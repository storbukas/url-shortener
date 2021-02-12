<h1 align="center">
  <br>
  :link:
  <br>
</h1>

<h4 align="center">A website for <a href="https://fiy.no/" target="_blank">URL shortener</a>.</h4>

<p align="center">
  <a href="https://fiy.no/">
    <img src="https://img.shields.io/website-up-down-green-red/http/fiy.no.svg">
  </a>
  <a href="https://opensource.org/licenses/MIT">
      <img src="https://img.shields.io/badge/License-MIT-blue.svg">
  </a>
</p>

# URL shortener

URL shortener with Jekyll and Github pages

> Create short URLs that can be easily shared, tweeted, or emailed to friends. Fork this repo to get started.

## Getting Started

Follow these steps to create your own URL Shortener:

1. Get a domain name
2. Configure the DNS for the domain
3. Fork or clone this repo
4. Edit the `_config.yml` file
5. Host on GitHub Pages
6. Create link pages

### Domain

Get a *(preferably short)* domain name from your favorite [registrar](https://www.icann.org/registrar-reports/accredited-list.html).

Add CNAME

### Configuration

Edit the `_config.yml` file:

```yml
name: URL Shortener

title: URL Shortener
description: Create short URLs that can be easily shared, tweeted, or emailed to friends.

version: v0.1

baseurl: ""
permalink: /:slug/

plugins:
  - jekyll-redirect-from

collections:
  urls:
    output: true
    permalink: /:slug

whitelist:
  - jekyll-redirect-from

redirect_from:
  json: false

include:
  - _urls
```

The global `permalink` for pages is set to `/:slug/`.

> Permalinks are the output path for your pages, posts, or collections. They allow you to structure the directories of your source code different from the directories in your output.

> Slugified title from the document’s filename (any character except numbers and letters is replaced as hyphen). May be overridden via the document’s `slug` front matter.

Read more about permalinks at https://jekyllrb.com/docs/permalinks/

It is the `jekyll-redirect-from` plugin that does the redirecting from the *short link* to the *target page*.

> Sometimes, you may want to redirect a site page to a totally different website.

Read more about the plugin at https://github.com/jekyll/jekyll-redirect-from

You can find more useful `plugins` to add at https://pages.github.com/versions/

When running Jekyll locally, uncomment the `repository` line and point to your own GitHub repo.

### GitHub Pages

Go to the repo [/settings](../../settings) and scroll down to the **GitHub Pages** section.

Set the `Source` to `master branch`: https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/

Point the `Custom domain` to your domain name: https://help.github.com/articles/using-a-custom-domain-with-github-pages/

This will create a `CNAME` file in the repo:

```txt
example.com
```

> Custom domains are stored in a `CNAME` file in the root of your repository. You can add or update your custom domain through your repository settings. You can also edit the file directly to update your custom domain.

Read more about adding a custom domain at https://help.github.com/articles/adding-or-removing-a-custom-domain-for-your-github-pages-site/

Make sure the `Enforce HTTPS` checkbox is ticked: https://help.github.com/articles/securing-your-github-pages-site-with-https/

> HTTPS provides a layer of encryption that prevents others from snooping on or tampering with traffic to your site. When HTTPS is enforced, your site will only be served over HTTPS.

Read more about GitHub Pages at https://pages.github.com

## Links

Create a new short link by creating a page: https://jekyllrb.com/docs/pages/

Create the file in the _urls folder of the repository.

This repository has an example, [`repo.md`](repo.md):

```md
---
redirect_to: https://github.com/storbukas/url-shortener
---
```

This results in:

* "Short" link: https://fiy.no/repo
* Target page:  https://github.com/storbukas/url-shortener

The `redirect_to` is the URL to the target page. This is the only [front matter](https://jekyllrb.com/docs/front-matter/) that is mandatory to make the short link work.

The file can have a `.md` (Markdown) or `.html` extension.

By default, the file name will be the *slug* of the short link. This behavior is configured in `_config.yml`.

If you want to use a different slug, set the `permalink` variable:

```md
permalink: /something/
```

Take the opportunity to get a real short slug by using *emojis*:

```md
permalink: /😻/
```

Find appropriate emojis to copy from https://www.emojicopy.com

## Built With

* Jekyll: https://jekyllrb.com
* jekyll-redirect-from: https://github.com/jekyll/jekyll-redirect-from
* GitHub Pages: https://pages.github.com

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT) - see the [LICENSE](LICENSE) file for details

## Credits

- [hlaueriksson](https://github.com/hlaueriksson)/[jekyll-url-shortener](https://github.com/hlaueriksson/jekyll-url-shortener) - Inspired and based upon 