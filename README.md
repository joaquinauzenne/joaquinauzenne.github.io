# joaquinauzenne.github.io

Personal portfolio website for **Joaquin Auzenne** — bioinformatician, applied mathematician, and open scientist at the University of Texas at Austin.

Live at: **[joaquinauzenne.github.io](https://joaquinauzenne.github.io)**

---

## Origin & Attribution

This site was originally forked from [Academic Pages](https://github.com/academicpages/academicpages.github.io), a GitHub Pages template for academic portfolios based on the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) Jekyll theme (© 2016 Michael Rose, MIT License).

The site has since been fully redesigned with a custom Jekyll theme. The Academic Pages collections system, layouts, SCSS, and includes have been replaced entirely. Only the repository scaffolding and deployment infrastructure were retained from the fork.

---

## Site Architecture

Single-page Jekyll site with the following sections (in order):

| Section | Include | Data Source |
| --- | --- | --- |
| Nav | `_includes/nav.html` | `_config.yml` author info |
| Hero | `_includes/hero.html` | `_data/hero.yml` |
| About | `_includes/about.html` | `index.md` content + `_data/about_sidebar.yml` |
| Experience | `_includes/experience.html` | `_data/experience.yml` |
| Skills | `_includes/skills.html` | `_data/skills.yml` |
| Projects | `_includes/projects.html` | `_data/projects.yml` |
| Contact | `_includes/contact.html` | `_config.yml` author info |
| Footer | `_includes/footer.html` | `_config.yml` author info |

### Key Files

- `_config.yml` — Site settings and author info (name, emails, GitHub, LinkedIn, phone, location)
- `_layouts/default.html` — Main layout; assembles all includes, links compiled CSS
- `_sass/main.scss` — All custom styles (variables, layout, components, animations, responsive)
- `assets/css/main.scss` — Jekyll SCSS entry point (imports `_sass/main.scss`)
- `index.md` — About section body text (rendered via `{{ content }}` in `about.html`)
- `files/Auzenne_CV.pdf` — CV PDF, linked via the "Download CV" button in the hero section

### Design

- **Fonts:** DM Serif Display · DM Sans · DM Mono (Google Fonts)
- **Colors:** Cream `#F5F0E8` · Ink `#1A1712` · Moss `#3D5A3E` · Clay `#B8703A` · Sand `#D9C9A8`
- **SCSS:** Compiled via Jekyll's standard pipeline (`assets/css/main.scss` → `_sass/main.scss`)

---

## Changes from the Academic Pages Fork

- Replaced the Minimal Mistakes / Academic Pages theme with a fully custom HTML/CSS/SCSS design
- Removed all Academic Pages collections (publications, talks, teaching, portfolio)
- Replaced `_layouts/`, `_includes/`, and `_sass/` entirely with custom files
- Replaced `assets/css/main.scss` (which imported Academic Pages vendor SCSS) with a simple `@import "main"` pointing to the new `_sass/main.scss`
- Simplified `_config.yml` to remove Academic Pages-specific settings
- Simplified `Gemfile` to use only the `github-pages` gem
- All content is editable via `_data/*.yml` files and `index.md` — no HTML changes needed for content updates

---

## Running Locally

Requires Ruby and Bundler.

```bash
bundle install
bundle exec jekyll serve
```

Then open [http://localhost:4000](http://localhost:4000).

> On Ruby 3.x you may need `gem 'webrick'` in your Gemfile (already included).

---

## Editing Content

| What to change | Where |
| --- | --- |
| Hero eyebrow, tagline, stats, interest tags | `_data/hero.yml` |
| About sidebar cards (learning, interests, languages, education summary) | `_data/about_sidebar.yml` |
| Experience timeline (research, professional, education tabs) | `_data/experience.yml` |
| Skills cards | `_data/skills.yml` |
| Project cards | `_data/projects.yml` |
| About section body text | `index.md` |
| Contact info, social links, author details | `_config.yml` under `author:` |
| CV PDF | Replace `files/Auzenne_CV.pdf` |

---

## Deployment

Deployed automatically to GitHub Pages on every push to `master`. No custom Actions workflow is needed — GitHub Pages detects the `github-pages` gem and builds with Jekyll.
