![DNB-Hugo/HEAD](.github/github-card-dark.png#gh-dark-mode-only)
![DNB-Hugo/HEAD](.github/github-card-light.png#gh-light-mode-only)

# GoHugo Component / Search Algolia

This is a Hugo theme component with helpers to add an [Algolia powered search](https://www.algolia.com/) to your website.

## Installing

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
