# cway14.github.io

Personal developer profile built with Jekyll, hosted on GitHub Pages.

## Structure

- `index.md` — About / Home
- `resume.md` — Resume page with PDF embed
- `projects.md` — Projects (data from `_data/projects.yml`)
- `blog.md` — Blog listing
- `_posts/` — Blog posts (YYYY-MM-DD-title.md)
- `assets/resume/resume.pdf` — Your resume PDF (replace the placeholder)

## Local Development

```bash
gem install bundler jekyll
bundle init
bundle add jekyll minima
bundle exec jekyll serve
```

Then open http://localhost:4000.

## Updating Content

- **Resume:** Replace `assets/resume/resume.pdf` with your actual PDF
- **Projects:** Edit `_data/projects.yml`
- **Blog posts:** Add markdown files to `_posts/` with `YYYY-MM-DD-title.md` naming
