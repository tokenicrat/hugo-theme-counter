# Counter

A minimalist Hugo theme inspired by [Wang Yin's Blog](https://www.yinwang.org/) style.

> This README is translated by AI. Inaccurate information may exist.
> 
> Moreover, menu and typography designs in this theme is dedicated to Chinese, so consider other themes before using it for an English site.

## Quick Start

Execute the following in your existing Hugo site:

```bash
git clone https://github.com/tokenicrat/hugo-theme-counter.git themes/counter
```

Then modify your `hugo.yaml`:

```yaml
theme: counter
```

## Configuration

Add the following to your `hugo.yaml`:

```yaml
taxonomies:
  topic: topics # equivalent to tags

params:
  titleImage: "/title.png" # Title image in the top-left corner, transparent background recommended
  favicon: "/favicon.png" # Website icon
  menu: # Menu items
    - name: "❓ About"
      url: "/about"
    - name: "🚏 Topics"
      url: "/topics"
    - name: "🔭 Archives"
      url: "/archives"
  footer: true # Whether to display the footer
```

### Content Organization

This theme uses a special content organization structure:

- The homepage displays groups (blog groups), which are directories under `content`:
  
  ```
  content
  |- books
     |- _index.md # Set blog group title here
  |- movies
     |- _index.md
     |- forrest_gump.md
  ```
  
  In `_index.md`, you can customize the title, summary text, and category page content:

  ```markdown
  ---
  title: Books
  summary: Books I like
  ---

  Some introduction about this category.
  ```
- Time-ordered archives are at `/archives`, which can also be customized in `content/archives/_index.md`
- Tags (topics) are at `/topics`, customizable in `content/topics/<TOPIC_NAME>/_index.md`

Additionally, homepage information can be customized in `content/_index.md`.

### Additional Configuration

This theme is relatively basic, and some settings require you to modify the theme directory directly.

- `themes/counter/layouts/partials/comment.html`: Comment plugin, just paste the HTML directly
- `.../footer.html`: Footer
- `.../head.html`: KaTeX support, can be removed if not needed
  To use KaTeX in a blog post, add `katex: true` in the front matter

Due to the author's limited CSS skills, the styling is minimal with many default values, and the colors might not be optimal. Please modify as needed.

## Troubleshooting

If Hugo indicates that your version is too low during site building, it's because the author lazily set the minimum version to `0.148.1` in `theme.toml`. Your older Hugo version will likely work fine - just modify the version number.

## License

The Unlicense
