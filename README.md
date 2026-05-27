# mikkuzne.github.io

Personal site for Mikhail Kuznetsov — built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme.

Live at **https://mikkuzne.github.io** once deployed.

## Editing

- `_pages/about.md` — landing page bio.
- `_pages/cv.md` — CV web summary; the canonical CV lives at `assets/pdf/cv.pdf` (rebuilt from `~/personal/kuznetsov_cv.tex` on the home box).
- `_bibliography/papers.bib` — publications. Add a new entry and it shows on `/publications/`.
- `_news/announcement_*.md` — news items on the about page (inline if `inline: true`).
- `_projects/*.md` — project cards on `/projects/`.
- `_data/socials.yml` — email, Scholar, GitHub, LinkedIn.

## Deploy

Push to `main`. GitHub Actions (`.github/workflows/deploy.yml`) builds Jekyll + purges unused CSS and publishes to `gh-pages`.

## Build locally (optional — only if you install Ruby)

```bash
bundle install
bundle exec jekyll serve
```

Day-to-day editing doesn't need this; just push and let Actions build.
