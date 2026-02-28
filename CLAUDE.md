# CLAUDE.md — Project Context

## Project Overview

Joaquin Auzenne's personal portfolio website, live at `joaquinauzenne.github.io` via GitHub Pages. Originally forked from [Academic Pages](https://github.com/academicpages/academicpages.github.io) (Minimal Mistakes), then fully redesigned as a custom Jekyll theme. The site **builds and deploys successfully** as of the last session.

---

## Design System

- **Fonts:** DM Serif Display (headings/display), DM Sans (body), DM Mono (labels/mono)
- **Palette:** `$cream` #F5F0E8 · `$ink` #1A1712 · `$moss` #3D5A3E · `$clay` #B8703A · `$sand` #D9C9A8 · `$fog` #E8E0D0 · `$accent` #6B8F71
- **Layout:** single-page with anchor sections — Hero → About → Experience → Skills → Projects → Contact → Footer

---

## Architecture

### Build Pipeline

- `Gemfile` uses `gem 'github-pages'` (GitHub Pages compatible)
- SCSS is compiled via the **standard Jekyll pipeline**: `assets/css/main.scss` (empty frontmatter) imports `_sass/main.scss`
- `_layouts/default.html` links the compiled CSS with `<link rel="stylesheet" href="{{ '/assets/css/main.css' | relative_url }}"/>`

### Key Files

| File | Role |
| --- | --- |
| `_config.yml` | Site settings, author info, `collections: projects` |
| `_layouts/default.html` | Main single-page layout; includes all section partials |
| `_layouts/project.html` | Per-project detail page layout |
| `_includes/nav.html` | Fixed top nav |
| `_includes/hero.html` | Hero section (profile photo, stats, interest tags) |
| `_includes/about.html` | About section; renders `{{ content }}` from `index.md` |
| `_includes/experience.html` | Tabbed experience section (Research / Professional / Education) with Download CV link |
| `_includes/skills.html` | Skills grid from `_data/skills.yml` |
| `_includes/projects.html` | Projects grid — loops `site.projects` (Jekyll collection) |
| `_includes/contact.html` | Contact section |
| `_includes/footer.html` | Footer |
| `_sass/main.scss` | All styles |
| `assets/css/main.scss` | Entry point (empty frontmatter + `@import "main"`) |
| `index.md` | Homepage; `layout: default`; body renders into About section |

### Data Files

| File | Drives |
| --- | --- |
| `_data/hero.yml` | Hero eyebrow text, tagline, stats (num + label), interest tags |
| `_data/about_sidebar.yml` | About sidebar cards (Currently Learning, Research Interests, Languages, Education) |
| `_data/experience.yml` | Three tab arrays: `research`, `professional`, `education` (timeline items with `title`, `org`, `date`, `bullets`) |
| `_data/skills.yml` | Skill cards with `title` + `tags` list |

### Jekyll Collection — Projects

Projects are a **Jekyll collection** (`_projects/`), not a data file. Each project is a Markdown file with frontmatter + editable body content.

- Collection registered in `_config.yml`: `output: true`, `permalink: /projects/:name/`
- Each file lives at `_projects/[slug].md`
- Frontmatter fields: `layout: project`, `title`, `org`, `desc` (card summary), `tags`
- The Markdown body is the full detail page content
- Cards on the homepage link to `/projects/[slug]/` via `_layouts/project.html`

#### Current Projects

| Slug | Title |
| --- | --- |
| `covid-19-network-dynamics` | COVID-19 Spatiotemporal Network Dynamics |
| `mammalian-metabarcoding` | Mammalian Metabarcoding & Species-Range Visualization Platform |
| `idminer` | IdMiner — Bioinformatic Literature Search Tool |
| `longhorn-racing` | Longhorn Racing — Composites Division |
| `methanotroph-metabolic-engineering` | Methanotroph Metabolic Engineering |

---

## How to Edit Content

| What to change | Where |
| --- | --- |
| Hero text, stats, interest tags | `_data/hero.yml` |
| About sidebar cards | `_data/about_sidebar.yml` |
| About body text | `index.md` |
| Experience timeline bullets | `_data/experience.yml` |
| Skill cards | `_data/skills.yml` |
| Project card summary / tags | Frontmatter in `_projects/[slug].md` |
| Project detail page body | Markdown body in `_projects/[slug].md` |
| Add a new project | Create `_projects/[new-slug].md` with required frontmatter |
| Contact info / social links | `_config.yml` under `author:` |
| Download CV file | Replace `files/Auzenne_CV.pdf` |
| Profile photo | Replace `images/profile.png` (displayed at 220×220px, circular) |

---

## Author Info

- **Name:** Joaquin Auzenne
- **Work email:** <auzenne.work@gmail.com>
- **Academic email:** <joaquinauzenne@utexas.edu>
- **GitHub:** joaquinauzenne
- **LinkedIn:** auzenneworks
- **Location:** Austin, TX
- **Affiliation:** University of Texas at Austin

---

## Git / Deployment

- **Remote:** `git@github.com:joaquinauzenne/joaquinauzenne.github.io.git` (SSH)
- **Branch:** `master` → auto-deploys to GitHub Pages via Actions
- Push with: `git push origin master`
- To verify deploy: repo → Actions tab → latest workflow run

---

## Known Working State (end of last session)

- GitHub Pages build: **passing**
- All 5 project detail pages render at `/projects/[slug]/`
- Profile photo centered in hero rings at 220×220px
- Download CV button in experience tab bar (right-justified)
- SCSS compiled via standard Jekyll pipeline (no `scssify`)
