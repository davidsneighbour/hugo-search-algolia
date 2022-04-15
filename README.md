<!--- CARD BEGIN --->

![DNB-Hugo/HEAD](.github/github-card-dark.png#gh-dark-mode-only)
![DNB-Hugo/HEAD](.github/github-card-light.png#gh-light-mode-only)

<!--- CARD END --->

# David's Neighbour GoHugo Component / Search Algolia

This is a Hugo theme component with helpers to add an [Algolia powered search](https://www.algolia.com/) to your website.

### Installing

First enable modules in your own repository:

```bash
hugo mod init github.com/username/reponame
```

Then add this module to your required modules in config.toml.

```toml
[module]
[[module.imports]]
path = "github.com/davidsneighbour/hugo-search-algolia"
```

The next time you run `hugo` it will download the latest version of the module.

To make this component work you need to add Algolia to your home output formats:

```toml
[outputs]
home = [ ... others ... , "Algolia" ]
```

You already should have an `[output]` section, add `"Algolia"` to it. Do not add it anywhere other than in the `home` directive.

Adding the search to your content

`content/search/index.md`

```markdown
---
title: Search
description: Search in all articles
url: /search
---

{{< search >}}
```

Add your items to the search index

Install `atomic-algolia`:

```shell
npm install -D atomic-algolia
```

Once you configured your search index at algolia you can add new items in your deploy script. Add the following lines to your package.json (the sections might exist, so don't re-create them).

Add a script to your package.json configuration

```json
{
  "scripts": {
    "algolia": "hugo --quiet && atomic-algolia && rm -rf public"
  }
}
```

Add the index creation to your deployment process:

```shell
npm run algolia
```

### Updating

```shell
hugo mod get -u github.com/davidsneighbour/hugo-search-algolia
hugo mod get -u # update all modules
```

## Other [GoHugo](https://gohugo.io/) components by [@davidsneighbour](https://github.com/davidsneighbour/)

<!-- prettier-ignore -->
| Component | Description |
| :--- | :--- |
| [hugo-auditor](https://github.com/davidsneighbour/hugo-auditor) | |
| [hugo-debug](https://github.com/davidsneighbour/hugo-debug) :mage_man: | |
| [hugo-errors](https://github.com/davidsneighbour/hugo-errors) | |
| [hugo-feeds](https://github.com/davidsneighbour/hugo-feeds) | |
| [hugo-functions](https://github.com/davidsneighbour/hugo-functions) | |
| [hugo-giscus](https://github.com/davidsneighbour/hugo-giscus) | The Giscus comment system layout for GoHugo. |
| [hugo-head](https://github.com/davidsneighbour/hugo-head) | A GoHugo theme component that solves the old question of "What tags belong into the `<head>` tag of my website?" |
| [hugo-hooks](https://github.com/davidsneighbour/hugo-hooks) | GoHugo's missing hook system for template extensions. |
| [hugo-internals](https://github.com/davidsneighbour/hugo-internals) | Better internal templates for GoHugo |
| [hugo-netlification](https://github.com/davidsneighbour/hugo-netlification) | a collection of tools that optimize your site on Netlify |
| [hugo-opensearch](https://github.com/davidsneighbour/hugo-opensearch) | configuration for Open Search |
| [hugo-pictures](https://github.com/davidsneighbour/hugo-pictures) | |
| [hugo-pwa](https://github.com/davidsneighbour/hugo-pwa) | Automatically turns your site into a PWA |
| [hugo-renderhooks](https://github.com/davidsneighbour/hugo-renderhooks) | render hooks for Markdown markup |
| [hugo-robots](https://github.com/davidsneighbour/hugo-robots) | configure the content of your robots.txt with front matter |
| [hugo-schema](https://github.com/davidsneighbour/hugo-schema) | |
| [hugo-search-algolia](https://github.com/davidsneighbour/hugo-search-algolia) | |
| [hugo-security](https://github.com/davidsneighbour/hugo-security) | |
| [hugo-sitemap](https://github.com/davidsneighbour/hugo-sitemap) | |
| [hugo-social](https://github.com/davidsneighbour/hugo-social) | |
