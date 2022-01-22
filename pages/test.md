# A foodie's guide to Banff National Park and the Canadian Rockies

`class:summary`Integer placerat quam ac tellus cursus semper. Maecenas non iaculis purus, et pellentesque orci. Praesent euismod posuere risus, eget congue dui porttitor eget. Integer nec vehicula orci. Cras ornare molestie molestie. Vivamus faucibus turpis vitae quam fringilla euismod. Pellentesque nec laoreet ipsum. Sed eros neque, dictum commodo iaculis eu, eleifend quis mi. Nulla volutpat vel augue et pharetra. Maecenas tempor aliquet varius. Suspendisse ut ante et ipsum elementum varius eget sit amet massa.

![Emerald Lake](iamges/emerald-1800.webp)

`class:caption`Cilantro Cafe and Emerald Lake Lodge

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec dignissim rhoncus fringilla. Fusce pharetra, erat ut feugiat ullamcorper, purus elit varius sapien, nec convallis dui enim vel tortor. Curabitur consequat aliquam turpis, in efficitur risus iaculis ac. Vestibulum viverra finibus ex, et gravida nibh porttitor vel. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Nullam consectetur, turpis id varius imperdiet, sem erat tempus nunc, non tincidunt tellus mauris quis neque. Donec maximus, dolor eget dictum finibus, nibh sem iaculis lacus, ac sodales urna velit facilisis felis. Nulla eget lacus scelerisque, vulputate lectus vitae, mattis lectus. Vivamus scelerisque felis eu diam porta vulputate. Vivamus quam libero, sollicitudin at libero quis, laoreet porttitor nisi.

`class:wide`![Crawford Supercell](images/crawford-3840.webp)

`class:caption`The “Crawford Mothership” near Crawford, Nebraska, on 6 June 2020.

Quisque nulla lorem, vehicula quis tempor sed, sollicitudin vitae magna. Aliquam erat volutpat. Pellentesque mollis erat pharetra risus lacinia pulvinar. Pellentesque faucibus dolor sem, at volutpat nibh malesuada non. Aenean interdum neque ac fermentum condimentum. Vivamus blandit maximus odio vitae viverra. Curabitur orci libero, tempor at placerat quis, scelerisque quis elit. Pellentesque in felis sem. Maecenas posuere et ipsum in fringilla. Ut euismod, lacus ut rutrum elementum, nunc neque interdum ipsum, sit amet porta nunc leo vel est. Interdum et malesuada fames ac ante ipsum primis in faucibus. Suspendisse purus augue, luctus non dolor at, auctor euismod nibh. Etiam ultrices eu orci quis scelerisque. Curabitur dui nisl, efficitur sed lectus ac, tempus convallis erat. Vestibulum nisi eros, mattis in cursus id, convallis eget risus. Morbi nisi sapien, blandit a sagittis non, vulputate et sapien.

> Suspendisse purus augue, luctus non dolor at, auctor euismod nibh. Etiam ultrices eu orci quis scelerisque.

> Curabitur dui nisl, efficitur sed lectus ac, tempus convallis erat. Vestibulum nisi eros, mattis in cursus id, convallis eget risus. Morbi nisi sapien, blandit a sagittis non, vulputate et sapien.

`class:full`![Yosemite Sunset](images/yosemite-3840.webp)

`class:caption`A spectacular spring sunset at Yosemite National Park in May 2019.

Nullam consectetur, turpis id varius imperdiet, sem erat tempus nunc, non tincidunt tellus mauris quis neque. Donec maximus, dolor eget dictum finibus, nibh sem iaculis lacus, ac sodales urna velit facilisis felis. Nulla eget lacus scelerisque, vulputate lectus vitae, mattis lectus. Vivamus scelerisque felis eu diam porta vulputate. Vivamus quam libero, sollicitudin at libero quis, laoreet porttitor nisi.

## Restaurants

List of `restaurants`.

Vivamus venenatis urna quis rutrum pretium. Aliquam varius interdum massa vitae maximus. Phasellus placerat, ipsum at egestas lobortis, leo leo vestibulum neque, vel efficitur odio enim vel ipsum. Cras condimentum sapien risus, in egestas enim condimentum at. Integer quis elit ac purus porttitor tempus dictum id urna. Ut euismod at nulla id consequat. Integer egestas dolor eget facilisis commodo. Aenean purus magna, sagittis quis lobortis et, convallis in turpis. Sed gravida gravida diam, a tincidunt ipsum luctus eget. Mauris dignissim egestas nulla, non tempor mi iaculis id. Nam venenatis ac erat ac congue.

### The Bison

Vestibulum et dui a turpis scelerisque maximus eget at neque. Donec tincidunt sed nibh in rutrum. Nam quis est scelerisque, sagittis massa quis, efficitur nunc. Aliquam maximus dui eu faucibus posuere. Sed a tortor in purus dignissim semper. Integer commodo pretium erat consequat lacinia. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Duis turpis ante, tempus ut ipsum quis, ullamcorper ultrices est. Morbi bibendum lectus id molestie feugiat. Etiam eleifend nibh lorem, eget tempor diam auctor id. Cras id diam massa.

### Juniper Hill Bistro

Proin lacinia semper turpis sit amet aliquet. Duis molestie, mi id ullamcorper fermentum, enim tortor hendrerit lorem, ac interdum metus turpis et dui. Praesent ut nulla ut enim sagittis ornare quis ut nisi. Curabitur id lectus et tellus fringilla pharetra non a nisl. Pellentesque ullamcorper tellus vitae libero commodo venenatis. Pellentesque a turpis nec ligula rhoncus consectetur eget sit amet ipsum. Praesent pretium eleifend volutpat. Nulla ac fringilla velit. Maecenas nec ligula ut libero finibus porta id sed dolor. Suspendisse luctus massa eget nibh gravida, a luctus diam vestibulum. In efficitur dictum ex, quis sollicitudin velit fermentum nec. Sed commodo, nisl vitae suscipit porta, arcu ipsum commodo nibh, eget vulputate urna purus ut justo. Quisque cursus maximus felis eget luctus.

```
ffmpeg -i file.flv -c:v copy -c:a copy file.mp4
```

#### Another example

```
func enhance(writer io.Writer, node mdast.Node, entering bool) (mdast.WalkStatus, bool) { // Super extra long mega comment
	if h, ok := node.(*mdast.Heading); ok && entering {
		// Add permalinks to all headings
		permalink := &mdast.Link{}
		permalink.Destination = []byte("#" + h.HeadingID)
		permalink.AdditionalAttributes = []string{"class=\"permalink\""}
		children := h.GetChildren()
		children = append(children, permalink)
		h.SetChildren(children)
	}
	if a, ok := node.(*mdast.Link); ok && entering {
		// Prepend all local URLs with the base URL, except anchor links
		if len(a.Destination) > 0 && a.Destination[0] != '#' {
			a.Destination = []byte(BaseURL.With(string(a.Destination)))
		}
	}
	if img, ok := node.(*mdast.Image); ok && entering {
		// Prepend all images with the static URL
		img.Destination = []byte(StaticURL.With(string(img.Destination)))
	}

	return mdast.GoToNext, false
}
```

##### Heading 5

Vestibulum ac tellus porttitor, fringilla purus vitae, dictum neque. Curabitur urna sem, sollicitudin at faucibus eget, convallis et velit. Duis sodales sem sapien, at luctus nulla lobortis in. Vivamus nec arcu tristique, pulvinar est at, tristique ligula. Maecenas at elementum metus. Mauris non tristique ante. Sed eu mattis nisl.

###### Heading 6

Nunc sagittis nulla turpis, vel accumsan nulla semper sed. Aliquam ut sapien a sapien bibendum aliquam a faucibus orci. Sed eu diam non augue tristique blandit. Aliquam pretium, lectus in porta tempus, nisi nisi commodo elit, sed mattis tellus magna at nunc. In nec finibus neque, nec condimentum purus. Vivamus mattis enim sit amet libero suscipit, vitae aliquet velit imperdiet. Maecenas egestas ligula ac nisi suscipit, vel eleifend lorem malesuada. Ut vestibulum dapibus risus, et consequat tortor tincidunt vel. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Sed varius massa id erat finibus semper. Sed et ipsum porttitor, suscipit ligula id, aliquet metus. Phasellus ac faucibus mi.
