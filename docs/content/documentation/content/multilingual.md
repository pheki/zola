+++
title = "Multilingual sites"
weight = 130
+++

Zola supports having a site in multiple languages.

## Configuration
To get started, you will need to add the languages you want to support
to your `config.toml`. For example:

```toml
languages = [
    {code = "fr", rss = true}, # there will be a RSS feed for French content
    {code = "fr", search = true}, # there will be a Search Index for French content
    {code = "it"}, # there won't be a RSS feed for Italian content
]
```

If you want to use per-language taxonomies, ensure you set the `lang` field in their
configuration.

## Content
Once the languages are added in, you can start to translate your content. Zola
uses the filename to detect the language:

- `content/an-article.md`: this will be the default language
- `content/an-article.fr.md`: this will be in French

If the language code in the filename does not correspond to one of the languages configured,
an error will be shown.

If your default language has an `_index.md` in a directory, you will need to add a `_index.{code}.md`
file with the desired front-matter options as there is no language fallback.

## Output
Zola outputs the translated content with a base URL of `{base_url}/{code}/`.
The only exception to that is if you are setting a translated page `path` directly in the front-matter.
