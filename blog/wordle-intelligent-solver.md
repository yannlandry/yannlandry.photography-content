_(Not a photography article, but something interesting to share nonetheless.)_

[Wordle](https://www.powerlanguage.co.uk/wordle/) is a word game that was released in June 2021 and has since experienced a meteoric rise in popularity. By now, you've probably spotted the cryptic tweets and Facebook posts with the coloured squares:

>Wordle 219 3/6
>
>⬜⬜⬜🟨⬜<br />
>🟨🟨⬜🟩⬜<br />
>🟩🟩🟩🟩🟩<br />

Yes, that's the recent Wordle puzzle that stumped a good number of people on January 24th. And yes, I “solved” it in 3 guesses. More on that below.

Wordle is a daily challenge that requires players to guess a mystery 5-letter word in 6 tries or less. After each guess, the game informs the player of which letters were in the correct place, which letters are correct but in the wrong place, and which letters aren't part of the final word.

Add in a basic system to track playing and winning streaks, and a clever way to share results, but not answers, and you have an explosive cocktail.

I played Wordle a few times, but did not get hooked to the game itself. However, I really wanted to solve a different, one-time, much harder puzzle; how to build a program that could beat Wordle on demand? This was not about winning _once_, but about finding an exact strategy that works _every time_.

## The Wordle Solver

I decided to build the **[Wordle Solver](https://wordle.yannlandry.com)**. The Wordle Solver picks the best next word to guess at each round based on its findings from previous rounds.

The player still has to feed data back and forth between Wordle and the Solver, but otherwise the Solver is capable of playing an entire Wordle game on its own. And if you've already started today's puzzle and are stuck with only a few guesses remaining and no good word options on your mind, you can feed the Wordle Solver your previous guesses and let it guide you the rest of the way.

That Wordle 219 above was solved in 3 tries by the Wordle Solver. Easy like Sunday morning.

### Source code

The Wordle Solver is build entirely in pure HTML, CSS and JavaScript, with no backend. Not only can it be served by a standard host with extremely minimal resources, it can be executed pretty much anywhere.

Its source code is available on [GitHub](https://github.com/yannlandry/wordle-solver).

## Strategy

The rest of this article is more on the technical side.

Playing Wordle just a few times made it clear that the best way to progress forward in the game is by guessing individual letters, then guessing their position in the final word, then guessing the final word. Thus, when guessing a word, I have to maximize my chances that one or more letters are going to be in the final word.

In the field of artificial intelligence, there is a general approach for most problems; we use a search space with all possible actions and decisions, and pick the most advantageous of those actions according to a predefined set of criteria.

In this case, the search space is the list of all accepted 5-letter words. And since some letters occur more frequently than others, we pick the word with the most common letters—the criterion—as our next guess/action. Words that are no longer possible answers are discarded, thus reducing the search space, until (hopefully) only one word remains, that word being the answer to the puzzle.

In Wordle 219, the first two guesses cover enough critical letters to reduce the set of possible answers to just one after 2 iterations. Although the puzzle seemed to confuse humans a great deal, for a computer program, it's an _easy_ problem.

### Accepted words

First, the Wordle Solver needs a list of words to form a search space. Fortunately, Wordle's list of accepted words is publicly accessible. Any word outside of that list will produce an invalid guess that doesn't count against the total number of guesses, so there's no point in having Wordle Solver even bother with those words. And if any of Wordle's answers is not in the Solver's vocabulary, then the Solver is 100% guaranteed to fail. Therefore, the Solver will base itself off Wordle's official words&mdash;similar to playing Scrabble with an official Scrabble dictionary.

There are in fact two lists of words in Wordle; one is a list of words that will one day be answers to the daily puzzle, and the other is a list of words that are accepted as guesses but will _never_ be answers. Upon closer examination, it seems that the answer list is most likely curated to include more common words whereas the list of allowed guesses is much larger and allows everything that could remotely be considered a word (like _aargh_). Allowed guesses will never be answers, but can be extremely useful in narrowing down the search space quickly. The list of answers is 2315 words long, which is enough to last the game 6 years.

Furthermore, I decided that the Solver would play with the exact same words as humans; using only the answers would be downright cheating because there is no way for the normal player to find out whether a particular word is a possible answer or just an allowed guess without looking at Wordle's source code. Both word lists combine to 12972 words which together form the initial search space.

### Picking the best next guess

I have already discussed this briefly but there has to be a formally defined procedure to comp through thousands of words and determine precisely which is the most optimal choioce.

For this, and for many other problems, I like to use scoring systems. I iterate over each possibility and assign it a score, then pick the option with the highest score (or lowest score, depending on the application). Words with more common letters (_A_, _E_, _R_, _S_, etc.) get higher scores, while words with rarer letters (_Q_, _Z_, _X_, etc.) score less.

First, the Solver iterates over all words that are remaining in the search space and counts how many times each letter appears across all those words. Then, for each word, it sums the score of each _unique_ letter, producing a word-level score. Repeated letters are only counted once, which means that the score of a word like _“HEALS”_ is the sum of the scores for letters _H_, _E_, _A_, _L_, and _S_, whereas the score for _“HELLO”_ only includes one _L_. This heavily prioritizes words with more diverse letters over words with repeated letters.

### Pruning invalid words

Once the result of a guess has been received by the Solver, the work of pruning the search space begins, and words that are no longer eligible as potential answers are removed from the search space.

* When there are green letters, words that have non-matching letters in green positions are pruned;
* When there are yellow letters, words that have matching letters in yellow positions are pruned (yellow means the letter exists but not in this position);
* When there are grey letters, words that have any of the grey letters are pruned;
* If a word has correct letters, but doesn't use up all the yellow letters, it is pruned.

For this step, we must also take into account how Wordle colours letters. If an answer has one _A_, but the guess has two _A_'s, the first A is coloured yellow (or green if it's in the correct position) and the second A is greyed out. If the second A is in the correct position, it is coloured green, and the first one is greyed out.

### Potential weaknesses and alternative strategies

This type of aggressive pruning has the potential to backfire; for example, there are words that can still yield very valuable data but are pruned from the search space due to a few invalid characters. In fact, some Wordle players have even discussed that they sometimes start with two completely different answers in the first 2 rounds to eliminate/include a maximum number of common letters. This strategy could be implemented but would also require logic to decide when to switch from guessing impossible answers to actually trying to find the final word.

### An improvement: the tie-breaking mechanism

There are occasions where multiple words resemble one another and the Solver is left to pick within a search space that is very small but where multiple words are heavily similar (e.g. _NATAL_, _NAHAL_, _NAVAL_, _NASAL_). The tie-breaking mechanism is an improvement I added to the Solver that kicks in when the search space contains 7 words or less and prioritizes the words with the most common letters _in the original search space_ with the idea that words with overall more common letters are more likely to be part of Wordle's answer list.

### The unsolvables: the WIGHT case

_WIGHT_ is a possible answer to Wordle (meaning it will be a daily puzzle one day), and it takes no less than 13 guesses for the Wordle Solver to find.

The sequence of guesses starts with _AEROS_, _UNITY_, and _GITCH_. At this point the Solver has already nailed 4 out of the 5 letters. However, there are still at least 10 other words that end in _-ITCH_ that the Solver must try. As _W_ is a fairly rare letter in the word list, and in the English language in general, practically every other letter gets tried first. The sequence of guesses goes through _BIGHT_, _DIGHT_, _FIGHT_, _LIGHT_, _TIGHT_, _PIGHT_, _MIGHT_, _HIGHT_, _KIGHT_, and finally concludes with _WIGHT_.

## Results

Once I completed my first iteration of the Wordle Solver and gathered a few manual results, I wrote a [benchmarking](https://wordle.yannlandry.com/benchmark.html) tool to try out every possible answer for the next 6 years, and also every allowed guess as if it was a word. I was not able to reach the 95%+ win rate I was hoping for, but with the tie-breaker improvement mentioned above, I got very close.

The win rate when tested against the list of possible answers (aka real world scenarios) is **93.7%** while the win rate when tested against the list of all possible words is just above **87%**. I judge that this is still sufficient to release the Wordle as a worthy helper tool for struggling players, and hopefully future improvements will bring the win rate close to 100%.

I also tested the Solver against the [Adversarial Wordle](https://qntm.org/files/wordle/), a version of the game that changes the answer at every round to stretch the game as long as possible, and the Solver is capable of ultimately winning as its search space is reduced to 1.

### Detailed results

Those are the best results achieved with the current strategies and improvements:

| Wins in...        | %     |
| ----------------- | ----- |
| 2 guesses         | 1.2%  |
| 3 guesses or less | 17.5% |
| 4 guesses or less | 55.5% |
| 5 guesses or less | 82.5% |
| 6 guesses or less | 93.7% |
| Losses            | 6.3%  |

`class:center`**Average number of guesses:** 4.5

#### Using all answers as the search space

I modified the search space to only include possible answers just to see what would come out, and that brought the win rate to 99.1%. Of course, this is unrealistic for average players who wouldn't have access to the list of answers.

## Further improvement ideas

I have begun to think of several ideas to improve the accuracy and speed of the Solver...

* When scoring, do not only count the frequency of letters but also weigh their positions. The Wordle Solver always proposes _AEROS_ as the first guess, but _AROSE_ also contains all of the same letter. And if there are more words that end in _E_ than words that have _E_ as their second letter, guessing _AROSE_ might reduce the search space quicker than _AEROS_.

* ~~When scoring, do not score letters that are in green because those are settled; instead, focus on letters that haven't been found yet. This seems like the most promising option and the easiest to implement.~~ _Tried this, and it brought down the win rate to 92.6%._

Do you have any ideas that could improve the Wordle Solver?
