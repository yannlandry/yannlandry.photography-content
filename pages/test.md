# A foodie's guide to Banff National Park and the Canadian Rockies

`class:summary`Integer placerat quam ac tellus cursus semper. Maecenas non iaculis purus, et pellentesque orci. Praesent euismod posuere risus, eget congue dui porttitor eget. Integer nec vehicula orci. Cras ornare molestie molestie. Vivamus faucibus turpis vitae quam fringilla euismod. Pellentesque nec laoreet ipsum. Sed eros neque, dictum commodo iaculis eu, eleifend quis mi. Nulla volutpat vel augue et pharetra. Maecenas tempor aliquet varius. Suspendisse ut ante et ipsum elementum varius eget sit amet massa.

`class:image`![Emerald Lake](images/emerald-1800.webp)

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

<p><blockquote class="instagram-media" data-instgrm-captioned data-instgrm-permalink="https://www.instagram.com/p/CYRwGFmNXrK/?utm_source=ig_embed&amp;utm_campaign=loading" data-instgrm-version="14" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px auto; max-width:540px; min-width:326px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:16px;"> <a href="https://www.instagram.com/p/CYRwGFmNXrK/?utm_source=ig_embed&amp;utm_campaign=loading" style=" background:#FFFFFF; line-height:0; padding:0 0; text-align:center; text-decoration:none; width:100%;" target="_blank"> <div style=" display: flex; flex-direction: row; align-items: center;"> <div style="background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 40px; margin-right: 14px; width: 40px;"></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 100px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 60px;"></div></div></div><div style="padding: 19% 0;"></div> <div style="display:block; height:50px; margin:0 auto 12px; width:50px;"><svg width="50px" height="50px" viewBox="0 0 60 60" version="1.1" xmlns="https://www.w3.org/2000/svg" xmlns:xlink="https://www.w3.org/1999/xlink"><g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"><g transform="translate(-511.000000, -20.000000)" fill="#000000"><g><path d="M556.869,30.41 C554.814,30.41 553.148,32.076 553.148,34.131 C553.148,36.186 554.814,37.852 556.869,37.852 C558.924,37.852 560.59,36.186 560.59,34.131 C560.59,32.076 558.924,30.41 556.869,30.41 M541,60.657 C535.114,60.657 530.342,55.887 530.342,50 C530.342,44.114 535.114,39.342 541,39.342 C546.887,39.342 551.658,44.114 551.658,50 C551.658,55.887 546.887,60.657 541,60.657 M541,33.886 C532.1,33.886 524.886,41.1 524.886,50 C524.886,58.899 532.1,66.113 541,66.113 C549.9,66.113 557.115,58.899 557.115,50 C557.115,41.1 549.9,33.886 541,33.886 M565.378,62.101 C565.244,65.022 564.756,66.606 564.346,67.663 C563.803,69.06 563.154,70.057 562.106,71.106 C561.058,72.155 560.06,72.803 558.662,73.347 C557.607,73.757 556.021,74.244 553.102,74.378 C549.944,74.521 548.997,74.552 541,74.552 C533.003,74.552 532.056,74.521 528.898,74.378 C525.979,74.244 524.393,73.757 523.338,73.347 C521.94,72.803 520.942,72.155 519.894,71.106 C518.846,70.057 518.197,69.06 517.654,67.663 C517.244,66.606 516.755,65.022 516.623,62.101 C516.479,58.943 516.448,57.996 516.448,50 C516.448,42.003 516.479,41.056 516.623,37.899 C516.755,34.978 517.244,33.391 517.654,32.338 C518.197,30.938 518.846,29.942 519.894,28.894 C520.942,27.846 521.94,27.196 523.338,26.654 C524.393,26.244 525.979,25.756 528.898,25.623 C532.057,25.479 533.004,25.448 541,25.448 C548.997,25.448 549.943,25.479 553.102,25.623 C556.021,25.756 557.607,26.244 558.662,26.654 C560.06,27.196 561.058,27.846 562.106,28.894 C563.154,29.942 563.803,30.938 564.346,32.338 C564.756,33.391 565.244,34.978 565.378,37.899 C565.522,41.056 565.552,42.003 565.552,50 C565.552,57.996 565.522,58.943 565.378,62.101 M570.82,37.631 C570.674,34.438 570.167,32.258 569.425,30.349 C568.659,28.377 567.633,26.702 565.965,25.035 C564.297,23.368 562.623,22.342 560.652,21.575 C558.743,20.834 556.562,20.326 553.369,20.18 C550.169,20.033 549.148,20 541,20 C532.853,20 531.831,20.033 528.631,20.18 C525.438,20.326 523.257,20.834 521.349,21.575 C519.376,22.342 517.703,23.368 516.035,25.035 C514.368,26.702 513.342,28.377 512.574,30.349 C511.834,32.258 511.326,34.438 511.181,37.631 C511.035,40.831 511,41.851 511,50 C511,58.147 511.035,59.17 511.181,62.369 C511.326,65.562 511.834,67.743 512.574,69.651 C513.342,71.625 514.368,73.296 516.035,74.965 C517.703,76.634 519.376,77.658 521.349,78.425 C523.257,79.167 525.438,79.673 528.631,79.82 C531.831,79.965 532.853,80.001 541,80.001 C549.148,80.001 550.169,79.965 553.369,79.82 C556.562,79.673 558.743,79.167 560.652,78.425 C562.623,77.658 564.297,76.634 565.965,74.965 C567.633,73.296 568.659,71.625 569.425,69.651 C570.167,67.743 570.674,65.562 570.82,62.369 C570.966,59.17 571,58.147 571,50 C571,41.851 570.966,40.831 570.82,37.631"></path></g></g></g></svg></div><div style="padding-top: 8px;"> <div style=" color:#3897f0; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:550; line-height:18px;">View this post on Instagram</div></div><div style="padding: 12.5% 0;"></div> <div style="display: flex; flex-direction: row; margin-bottom: 14px; align-items: center;"><div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(0px) translateY(7px);"></div> <div style="background-color: #F4F4F4; height: 12.5px; transform: rotate(-45deg) translateX(3px) translateY(1px); width: 12.5px; flex-grow: 0; margin-right: 14px; margin-left: 2px;"></div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(9px) translateY(-18px);"></div></div><div style="margin-left: 8px;"> <div style=" background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 20px; width: 20px;"></div> <div style=" width: 0; height: 0; border-top: 2px solid transparent; border-left: 6px solid #f4f4f4; border-bottom: 2px solid transparent; transform: translateX(16px) translateY(-4px) rotate(30deg)"></div></div><div style="margin-left: auto;"> <div style=" width: 0px; border-top: 8px solid #F4F4F4; border-right: 8px solid transparent; transform: translateY(16px);"></div> <div style=" background-color: #F4F4F4; flex-grow: 0; height: 12px; width: 16px; transform: translateY(-4px);"></div> <div style=" width: 0; height: 0; border-top: 8px solid #F4F4F4; border-left: 8px solid transparent; transform: translateY(-4px) translateX(8px);"></div></div></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center; margin-bottom: 24px;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 224px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 144px;"></div></div></a><p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;"><a href="https://www.instagram.com/p/CYRwGFmNXrK/?utm_source=ig_embed&amp;utm_campaign=loading" style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none;" target="_blank">A post shared by Yann Landry (@yannlandry.photography)</a></p></div></blockquote> <script async src="//www.instagram.com/embed.js"></script></p>

###### Heading 6

Nunc sagittis nulla turpis, vel accumsan nulla semper sed. Aliquam ut sapien a sapien bibendum aliquam a faucibus orci. Sed eu diam non augue tristique blandit. Aliquam pretium, lectus in porta tempus, nisi nisi commodo elit, sed mattis tellus magna at nunc. In nec finibus neque, nec condimentum purus. Vivamus mattis enim sit amet libero suscipit, vitae aliquet velit imperdiet. Maecenas egestas ligula ac nisi suscipit, vel eleifend lorem malesuada. Ut vestibulum dapibus risus, et consequat tortor tincidunt vel. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Sed varius massa id erat finibus semper. Sed et ipsum porttitor, suscipit ligula id, aliquet metus. Phasellus ac faucibus mi.

[Internal link](/blog/new-website-blog)

[External link](https://github.com/yannlandry/yannlandry.photography)
