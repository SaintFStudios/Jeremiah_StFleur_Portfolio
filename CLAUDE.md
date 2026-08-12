# Jeremiah St. Fleur — Portfolio Site

## Repo
GitHub: `SaintFStudios/Jeremiah_StFleur_Portfolio`
Live: `https://saintfstudios.github.io/Jeremiah_StFleur_Portfolio/`
Branch: `main`

## Tech Stack
- Pure HTML/CSS/JS — no framework, no build step, no npm
- Hosted on GitHub Pages (static)
- Font Awesome 6.5.1 via CDN
- Google Fonts via CDN

## File Structure
```
index.html              ← Home page (hero, education, R&L timeline, project carousel, skills)
projects.html           ← Projects grid with filter buttons
teams.html              ← Teams card grid
gallery.html            ← Photo gallery
contact.html            ← Contact form
about.html              ← KEPT ON DISK but NOT linked anywhere (removed from all navs)

projects/
  scan-drone.html
  air-engine.html
  servo-motor.html
  robotic-arm.html
  potato-slicer.html
  mil-rover.html
  apollo.html

teams/
  high-strike.html
  terragator.html

css/style.css           ← All styles (single file)
js/main.js              ← Nav toggle, year, filter logic
images/                 ← All media (subdirs per project)
```

## Nav Links (all pages)
Home | Projects | Teams | Contact
- NO About link (about.html unlinked but kept on disk)
- NO Gallery link (gallery.html unlinked but kept on disk — in progress, not ready)
- Active page gets `class="active"` on its nav `<a>`

## Path Conventions
- Root pages (`index.html`, `projects.html`, etc.): `css/style.css`, `js/main.js`
- Subpages (`projects/*.html`, `teams/*.html`): `../css/style.css`, `../js/main.js`
- Back links: `<a href="../projects.html" class="back-link">` or `../teams.html`

## CSS Key Classes
- `.container` — max-width centered wrapper
- `.card` — base card style
- `.project-card`, `.project-card-header`, `.project-card-body` — project cards
- `.team-card`, `.team-card-header`, `.team-card-body` — team cards
- `.tag`, `.tags` — pill tags
- `.btn`, `.btn-outline` — buttons
- `.project-hero` — hero section for all detail pages (projects + teams)
- `.hero-label` — small label line above h1 on detail pages
- `.back-link` — arrow back link in detail page heroes
- `.project-meta` — icon + text meta row (date, category, etc.)
- `.project-body-content` — main content wrapper on detail pages
- `.media-grid.cols-2`, `.media-grid.cols-3` — image/video grids
- `.media-figure`, `.media-full` — figure wrappers
- `.timeline`, `.tl-item` — Research & Leadership timeline on index.html
- `.carousel-container`, `.carousel-viewport`, `.carousel-track` — home carousel
- `.carousel-btn`, `.carousel-dots`, `.carousel-dot` — carousel controls
- `.teams-grid` — auto-fill grid for team cards on teams.html
- `.site-nav`, `.nav-logo`, `.nav-links`, `.mobile-toggle` — navigation
- `.site-footer`, `.footer-links` — footer
- `.bg-light` — light background section

## CSS Custom Properties (in :root)
- `--primary-blue`, `--secondary-blue`
- `--primary-orange`, `--accent-orange`
- `--text-primary`, `--text-secondary`, `--text-muted`
- `--bg-primary`, `--bg-secondary`, `--bg-card`
- `--border-color`
- `--transition`

## Home Page Carousel
- 6 project cards auto-rotate every 4s
- Pauses on `mouseenter` on `.carousel-container`, resumes on `mouseleave`
- Prev/next buttons reset timer
- Responsive: 3 cards (>900px), 2 cards (≤900px), 1 card (≤540px)
- Card width computed via `getBoundingClientRect()` + 24px gap
- Dot indicators built dynamically by JS; one dot per possible stop position
- Inline `<script>` IIFE at bottom of index.html (before `</body>`)

## Education Block (index.html)
- University of Florida — B.S. Mechanical Engineering
- GPA: 3.64 / 4.00
- Status: Rising Senior — Expected Graduation: Aug 2027
- Coursework: Design & Manufacturing Lab, Circuits & Electronic Circuits I, Signals & Controls, Robot Geometry

## Projects (projects.html + individual pages)
All cards use `data-category="..."` for JS filter. Categories in use:
`robotics`, `design`, `academic`, `mechanical`, `controls`, `research`

| Card | Link | Category |
|------|------|----------|
| S.C.A.N. Drone | projects/scan-drone.html | robotics controls |
| Air Engine | projects/air-engine.html | mechanical design |
| 360° Servo Motor | projects/servo-motor.html | robotics mechanical |
| Robotic Arm | projects/robotic-arm.html | robotics design |
| Potato Slicer | projects/potato-slicer.html | design academic |
| MIL Rover (TerraGator) | projects/mil-rover.html | robotics research |
| Apollo (placeholder) | projects/apollo.html | design |
| High-Strike | teams/high-strike.html | design academic |

## Teams (teams.html + individual pages)
| Card | Link | Status |
|------|------|--------|
| High-Strike Group Project | teams/high-strike.html | Done |
| TerraGator — MIL | teams/terragator.html | Done |

## Footer (all pages)
Links: LinkedIn (`linkedin.com/in/jstfleur`), GitHub (`github.com`), 3D Print Club (`3dprintclub.org`), Email (`Jeremiahstfleur@ufl.edu`)
Year: `<span id="currentYear"></span>` — populated by main.js
NO "This portfolio demonstrates..." text anywhere (removed site-wide)

## Caveman Mode
User runs `/caveman` skill — respond with terse caveman speech. Drop articles/filler, keep all technical substance. Normal code, normal git commits.

## Git Workflow
- Commit to `main`, push to `origin main`
- If push rejected (diverged), use: `git pull --rebase origin main && git push origin main`
- Never force push to main
