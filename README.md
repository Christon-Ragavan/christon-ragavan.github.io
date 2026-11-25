# christon-ragavan.github.io

Personal site and blog of Christon Ragavan Nadar, built with Jekyll and hosted on GitHub Pages.
No theme gem: all layouts and styles live in this repo, so nothing breaks when a theme updates.

## Write a new post

1. Copy `_drafts/post-template.md` to `_posts/YYYY/YYYY-MM-DD-short-title.md` (one folder per year, e.g. `_posts/2026/`).
2. Fill in the front matter:

   ```yaml
   ---
   title: "My next post"
   date: 2026-12-01
   tags: [MLOps, Databricks]
   description: "One or two sentences for post lists and link previews."
   ---
   ```

3. Write in Markdown. Use `##` for sections (the title is already the page heading).
4. Commit and push to `master`. GitHub Pages rebuilds the site in a minute or two.

Unfinished posts can stay in `_drafts/`; they are never published.

### Popular posts on the home page

The home page shows posts three ways: **Latest**, **Popular** and **Topics** (filter by tag).
To put a post under Popular, add `popular: 1`, `popular: 2` or `popular: 3` to its front matter
(the number is its position). To take it off, delete the line. If no post has `popular`, the tab is hidden.
Topics are built from the `tags` of your posts automatically.

## Math

Math is on for every post (MathJax 3, full LaTeX).

| You want | Write |
|---|---|
| Inline math | `$$x_i$$` inside a sentence (`$x$` also works for simple cases) |
| Display equation | `$$` on its own line, the equation, `$$` on its own line, with a blank line before and after |
| Numbered equation | add `\tag{1}\label{eq:loss}` inside the display block |
| Reference | `$$\eqref{eq:loss}$$` |
| Multi-line | `\begin{aligned} ... \end{aligned}` inside a display block |

Two gotchas:

- `{{` and `{%` mean something to Jekyll. If an equation contains them, write `{ {` with a space, or wrap the block in `{% raw %}` … `{% endraw %}`.
- A `|` inside math in a Markdown table ends the cell. Use `\vert` or `\mid` instead.

To turn math off for a page, set `math: false` in its front matter.

## Update the rest of the site

| What | Where |
|---|---|
| Home page text | `index.md` |
| About page | `_pages/about.md` |
| CV (experience, skills, education) | `_data/cv.yml` |
| Publications | `_data/publications.yml` (add `url:` to make a title a link) |
| Projects | `_data/projects.yml` |
| Let's talk page | `_pages/talk.md`; set `booking_url` in `_config.yml` for a booking button |
| Name, email, LinkedIn, Scholar | `_config.yml` |
| Navigation | `_data/navigation.yml` |
| Colours and fonts | `assets/css/main.css` (top of the file) |
| Downloadable CV | put the PDF at `assets/files/cv.pdf`; the button on /cv/ appears automatically |

## Run it locally

```bash
bundle install
bundle exec jekyll serve --livereload --drafts
# open http://localhost:4000
```

## Preview pull requests

`netlify.toml` lets Netlify build a preview of every pull request. Connect the repo once at
app.netlify.com ("Add new site" → "Import from GitHub"); each PR then gets a preview link in a comment.
The live site keeps being served by GitHub Pages.
