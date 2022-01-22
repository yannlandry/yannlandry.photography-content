I have wanted to have a proper website and blog for a while as a more customized home on the Internet. I have tried having a blog a few times in the past but all were miserable failures, so I'm looking forward to see how this one will hold.

## Concept

This entire website is custom-built and designed using Golang with a few small plugins, and plain HTML, CSS and JavaScript. I spent some time weighing the options that existed:

* **Use a turnkey solution like Squarespace:** I think some website builders can produce great-looking results but unfortunately you're tied to the platform, their pricing, and whatever else could go wrong on their end. But if you don't have the technical capacities to build and run your custom platform, this is probably your best solution.

* **Use a CMS like WordPress:** This is still a very popular solution among many photographers. It's kind of a middle-ground between the solution listed above as you have the ease of managing the website but you're free to move around and host it wherever you please. However, given my needs I don't think I would be saving significant time building a WordPress site and choosing and tweaking a theme and heavy plugins that ultimately don't always work well together.

* **Build your own website from scratch:** This is still a painful solution but I think it can pay off in the long term. This way I have maximum control and can iterate very quickly as things change on the Internet. I explain this below more in detail.

This website is _very easy_ to deploy as it's basically just a couple Git repos that work together. I'm not depending on a heavy database, and the only “dynamic” content is the comments at the bottom of the website, for which I've chosen to rely on Disqus for now.

Here is a more in-depth view of the components. Everything is hosted on GitHub (but not deployed using GitHub pages).

### The web application

The web application is just a small Go program that serves semi-pre-rendered webpages. For my use case, this felt like a slightly better alternative to purely static pages as it allows me to add a couple dynamic elements (e.g. the publication date for blog posts). I start the application, that sits behind NGINX, and feed it the path of the website content as well as the base and static URLs for the website. The base URL is the actual URL you use to visit the website whereas the static URL is the URL where static content (images, scripts, styles) are hosted. You could feed it a different bundle of content and run an entirely different website.

Since this is only for personal use, the web application is not thoroughly documented but you can find it on [GitHub](https://github.com/yannlandry/yannlandry.photography).

### The content

The content is a set of directories arranged in a specified configuration. It's a collection of YAML, Markdown, and HTML template files specifying the website's actual _content_, such as pages, blog posts, and navigation. The web application loads the entire content into memory on startup (I might need to revisit this if the website grows too much) so content can be served extremely fast. Markdown is pre-rendered and templates are executed on request. If I want to update the website, I just pull the latest version of the content, and restart the web application.

You can also find the entirety of the contents of this website on [GitHub](https://github.com/yannlandry/yannlandry.photography-content).

### The static assets

As mentioned above, static assets are images, scripts, styles, etc. that define how the website _looks_. I could've probably just thrown the static assets in the content repository but right now it's separate. Static assets sit on the web server and are served by NGINX when the static URL is requested; I don't feed those into the Go web application.

All assets (except images) are hosted on [GitHub](https://github.com/yannlandry/yannlandry.photography-content).

## Future

I am hoping to update this website once in a while with trip reports, guides, tips, tutorials, and anything that comes to mind. I might also blog about tech and if that comes a major source of content I might just reuse the components above and build a tech-related blog.

Enjoy!
