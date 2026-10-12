# Making the Commonplace Visible

This repository contains a Jekyll site for introducing non-technical audiences to communication theory and its usefulness for everyday problems involving artificial intelligence. It is configured for the GitHub Pages repository `mattkorb6/primer`.

## Run the site locally

Requirements: Ruby, Bundler, and a working internet connection the first time dependencies are installed.

```sh
bundle install
bundle exec jekyll serve
```

Open <http://localhost:4000/primer/>. To build without starting a server:

```sh
bundle exec jekyll build
```

The generated site is written to `_site/`, which is ignored by Jekyll's configuration and should not be committed.

## Site map

- `index.html` is the home page and project introduction.
- `transmission/index.md` covers the transmission view and humanist critique.
- `meaning-and-culture/index.md` applies semiotics.
- `interpretation-and-power/index.md` applies Stuart Hall's encoding/decoding model.
- `interpretation-and-intention/index.md` introduces Eco and *intentio algorithmi*.
- `what-to-do/index.md` turns the lenses into personal and professional guidance.
- `how-this-site-was-built/index.md` documents the process and the agent's involvement.

## Adding and editing content

Each Markdown page begins with YAML front matter. Keep the `layout: page` line, then change the `title`, `kicker`, and `intro` to match your argument. Write the body below the second `---` using ordinary Markdown:

```markdown
## A section heading

Your paragraph goes here. Keep headings in order: use `##` for major sections and `###` for sections within them.

> A short quotation or claim can be highlighted this way.
```

The six pages are starter text, not finished scholarship. Replace the prompts with your own examples, citations, qualifications, and conclusions. Keep the practical link visible: explain what a theory lets an ordinary reader notice or do.

To add a new page, create a folder with an `index.md`, copy the front matter from an existing page, and add it to `_data/navigation.yml`:

```yaml
- title: "New page title"
	url: "/new-page/"
```

Use lowercase folder names with hyphens. Jekyll's `pretty` permalink setting makes `/new-page/` the public URL.

## Adding images

Put image files in `images/`. Prefer descriptive, lowercase filenames such as `community-workshop.jpg`. In Markdown, provide useful alternative text:

```markdown
![Three people comparing notes around a table]({{ '/images/community-workshop.jpg' | relative_url }})
```

Do not use an image as the only way to communicate an important idea. Keep a text equivalent in the page.

## Basic visual customization

The main variables are at the top of `assets/css/style.css`:

```css
:root {
	--ink: #202a25;
	--paper: #f4f0e7;
	--moss: #456956;
	--coral: #d7644c;
	--sun: #e8bd59;
}
```

Change these values to adjust the palette. Check contrast after changing them; body text should remain clearly readable against `--paper` and links should remain distinguishable without relying on color alone. The `--serif` and `--sans` variables control typography. The current fonts are loaded from Google Fonts; replace the import and variables if you prefer self-hosted fonts.

## GitHub Pages deployment

`.github/workflows/pages.yml` builds and deploys on every push to `main`, plus manual runs from the Actions tab. In the repository settings, set **Pages > Build and deployment > Source** to **GitHub Actions**. The repository and base URL are recorded in `_config.yml`:

```yaml
url: "https://mattkorb6.github.io"
baseurl: "/primer"
repository: "mattkorb6/primer"
github_username: "mattkorb6"
```

If the repository is renamed or moved, update those four values and any links should continue to build through Jekyll's `relative_url` filter.
