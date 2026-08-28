# CLAUDE.md — Project Context

## Project Overview

Joaquin Auzenne's personal portfolio website, live at `joaquinauzenne.github.io` via GitHub Pages. Originally forked from [Academic Pages](https://github.com/academicpages/academicpages.github.io), then fully redesigned twice — most recently (Aug 2026) as an **editorial multi-page site** based on a Claude Design Canvas mockup: short home statement, everything else behind links.

---

## Design System

- **Font:** a single serif family, `Academia` (self-hosted at `assets/fonts/academia/`, woff2/woff, roman + italic + bold), Georgia fallback — used for headings, body, and uppercase letter-spaced labels alike
- **Palette:** `$cream` #F5F0E8 · `$ink` #1A1712 · `$moss` #3D5A3E · `$clay` #B8703A · `$sand` #D9C9A8 · `$fog` #E8E0D0 · `$muted` #6E6A62 (body text) · `$blush` #FAC5C9 (home panel) · `$violet` #8C24C7 (motif dots)
- **Furniture:** noise-texture overlay, `fade-up` entrance animations, dot-and-rule dividers
- **Motif:** a DNA double helix — two mirrored strands with rungs between them. It appears tiled tall in the Home panel (`_includes/motif.svg`) and compact as the favicon (`images/favicon.svg`)
- **Layout:** multi-page — Home is a split hero (text left, blush motif panel + photo right); every other page is `eyebrow → H2 (italic em accent) → content` at `max-width: 78rem`

---

## Architecture

### Build Pipeline

- `Gemfile` uses `gem 'github-pages'` (GitHub Pages compatible)
- SCSS via the standard Jekyll pipeline: `assets/css/main.scss` (empty frontmatter) imports `_sass/main.scss`
- **libsass gotcha:** don't use CSS `min()`/`max()` with mixed units in SCSS (Sass tries to evaluate them and the build fails) — use `width` + `max-width` instead

### Pages & Layouts

| URL | Source file | Layout |
| --- | --- | --- |
| `/` | `index.md` | `home` (split hero + page index list) |
| `/about/` | `about.md` (bio markdown body) | `about` (grid: content + sidebar cards) |
| `/work/` | `work.md` | `page` + `_includes/work-list.html` |
| `/projects/[slug]/` | `_projects/[slug].md` | `project` (H2-split block rows) |
| `/experience/` | `experience.md` | `base` + `_includes/experience-body.html` |
| `/notes/` | `notes.md` | `page` + `_includes/notes-body.html` |
| `/contact/` | `contact.md` | `page` + `_includes/contact-body.html` |

- `_layouts/base.html` — shared chrome: `<head>`, nav (`_includes/nav.html`, active state from `page.url`), footer (`_includes/footer.html`). All other layouts nest inside it.
- `_layouts/page.html` — generic shell rendering `page.eyebrow`, `page.heading` (may contain `<em>`), optional `page.lede`, then `{{ content }}`.
- `_layouts/project.html` — fog header band (back link, number, title, org, tags), then splits the rendered markdown on `<h2>` boundaries: each `## Heading` in a project file becomes a sticky uppercase label beside its section body. Footer nav links to `/work/` and the next project.
- There is **no JavaScript** on the site (the old tab-switcher is gone; Experience shows all three groups sequentially).

### Data Files

| File | Drives |
| --- | --- |
| `_data/nav.yml` | Top nav **and** the numbered index list on Home (order = numbering) |
| `_data/hero.yml` | Home: eyebrow, `headline_lines`, Spinoza `quote`, `open_to` line, `show_motif`/`show_photo` toggles (legacy `stats`/`interests` kept but unrendered) |
| `_data/about_sidebar.yml` | About sidebar cards (Research Interests, Education, Languages) |
| `_data/experience.yml` | Experience groups: `research`, `professional`, `education` |
| `_data/skills.yml` | "Also in the toolkit" grid on Work (tags joined with " · ") |
| `_data/notes.yml` | Notes page: `reading`, `read`, `writing` |

### Jekyll Collection — Projects

- Registered in `_config.yml`: `output: true`, `permalink: /projects/:name/`
- Frontmatter: `layout: project`, `order` (display position on Work + numbering), `title`, `org`, `desc` (card blurb), `tags`
- Body is plain markdown; its `## Headings` (Overview, Methods / Approach, Key Results, Tools & Technologies) become the labeled blocks on the detail page

| Order | Slug |
| --- | --- |
| 1 | `mammalian-metabarcoding` |
| 2 | `covid-19-network-dynamics` |
| 3 | `idminer` |
| 4 | `methanotroph-metabolic-engineering` |
| 5 | `longhorn-racing` |

---

## How to Edit Content

| What to change | Where |
| --- | --- |
| Home headline, Spinoza quote, "open to" line | `_data/hero.yml` |
| Hide/show the motif or photo on Home | `show_motif` / `show_photo` in `_data/hero.yml` |
| Nav labels/order (and Home index numbering) | `_data/nav.yml` |
| About bio text | Markdown body of `about.md` |
| About sidebar cards | `_data/about_sidebar.yml` |
| Projects page intro line | `lede` frontmatter in `work.md` |
| Nav labels (e.g. "Projects" for `/work/`) | `label` in `_data/nav.yml` — the `url` stays `/work/` |
| Toolkit categories/tags | `_data/skills.yml` |
| Experience timeline bullets | `_data/experience.yml` |
| Reading list / writing entries | `_data/notes.yml` |
| Project card blurb / tags / position | Frontmatter (`desc`, `tags`, `order`) in `_projects/[slug].md` |
| Project detail page body | Markdown body of `_projects/[slug].md` (use `## Headings` to create blocks) |
| Add a new project | Create `_projects/[new-slug].md` with `layout: project` + `order` + frontmatter |
| Contact info / social links / references | `_config.yml` under `author:` |
| Page eyebrows & headings | Frontmatter of `about.md`, `work.md`, `notes.md`, `contact.md` (Experience's header lives in `_includes/experience-body.html`) |
| Download CV file | Replace `files/Auzenne_CV.pdf` |
| Profile photo | Replace `images/profile.png` (circular on Home) |
| Favicon | `images/favicon.svg` — the helix motif; keep it legible at 16px |

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
- **Local preview:** no local Ruby; use the Docker setup (`docker compose up --build`, port 4000) if a real Jekyll render is needed

## Known Working State (end of Aug 2026 redesign session)

- All pages verified in a local static preview (python-liquid render + libsass CSS), desktop and mobile
- SCSS compiles under libsass; YAML and Liquid statically validated
- The `Academia` font ships without a traceable license (user accepted the risk knowingly)
