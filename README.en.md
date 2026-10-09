<div align="center">
  <img src=".github/assets/icon.png" width="120" alt="Morning Star · Evening Star" />
  <h1>启明星-长庚星</h1>
  <p><b>sunfleeting's personal blog</b><br /><sub>The one before daybreak · everything fleeting, written down here</sub></p>
  <p>
    <a href="https://sunfleeting-debug.github.io/"><img src="https://img.shields.io/badge/live-sunfleeting--debug.github.io-2b2350" alt="Live"></a>
    <img src="https://img.shields.io/badge/Valaxy-1.0.0--rc.15-4b6bfb" alt="Valaxy">
    <img src="https://img.shields.io/badge/Vue-3-42b883" alt="Vue 3">
    <img src="https://img.shields.io/badge/build-Vite%20SSG-646cff" alt="Vite SSG">
    <img src="https://img.shields.io/badge/host-GitHub%20Pages-181717" alt="GitHub Pages">
  </p>
  <p>
    <a href="README.md">简体中文</a> ·
    <b>English</b>
  </p>
</div>

<p align="center">
  <img src=".github/assets/social-preview.png" alt="Morning Star · Evening Star — sunfleeting's personal blog" />
</p>

I write code, read books, and occasionally go outside to take pictures. This site is a place for all of that — no growth hacking, no content strategy, just somewhere I actually own.

The site is **pure static**: no backend, no database, no analytics. Every page is rendered at build time. Take a look at **[sunfleeting-debug.github.io](https://sunfleeting-debug.github.io/)**.

> **About this repository**: this is the **build-output repository** — GitHub Pages serves it directly. The source project (a Valaxy setup) lives in a private local workspace, so what you see at the root is a pile of generated `*.html` rather than `pages/*.md`. The README and its images are the only hand-maintained parts of this repo.

---

## At a glance

| | |
| --- | --- |
| **Live** | [sunfleeting-debug.github.io](https://sunfleeting-debug.github.io/) |
| **Stack** | [Valaxy](https://github.com/YunYouJun/valaxy) `1.0.0-rc.15` · Vue 3 · Vite SSG |
| **Theme** | [`valaxy-theme-yun`](https://github.com/YunYouJun/valaxy-theme-yun), with 36 custom components on top |
| **Hosting** | GitHub Pages (`main` / root, stable subdomain) |
| **Content** (as of Oct 2026) | 23 posts · 9 categories · 51 tags · 27 albums (916 photos) · 5 notes · 13 self-built mini-games |
| **Shape** | Static · no backend · no database · no tracking scripts |

---

## ✨ Features

### 📝 Writing & reading

- **Posts / archives / categories / tags** — organised by topic rather than by date.
- **Reading experience** — frosted-glass navbar, reading-progress indicator on the right edge, in-page table of contents, code highlighting and copy, image lightbox.
- **Reading-font switcher** — one click to cycle between three CJK font stacks (default / Songti / Kaiti). The choice persists, with a no-flash boot script.
- **Chinese typography** — paragraph spacing loosened, heading weight capped at 500 (CJK headings should not be bold), punctuation normalised. Articles migrated from WeChat keep their original look on purpose.

### 🖼 Albums

- **27 albums, 916 photos**, grouped by trip. A custom `layout: album` + `PhotoAlbum.vue` rather than the theme's built-in gallery.
- **Two-tier images** — thumbnails in the grid, full-size on open, so a page never pulls everything at once.
- **Lightbox** — arrow-key navigation, wrap-around paging, click-outside to close.

### 🎮 Game room

- **13 pure front-end mini-games**: Spider Solitaire, Minesweeper, Snake, Subway Runner, 2048, Tetris, Sudoku, Sokoban, Dino Run, Hill Climb Racing, Thunder Fighter, Match 3, Need for Speed.
- **Works offline**, no network calls, no score uploads — high scores stay in `localStorage`.
- Hill Climb's physics live in a standalone `hillclimb-physics.mjs` so they can be re-simulated headlessly in Node while tuning.

### 🔬 Research & projects

- **`/research`** — directions, ongoing projects and paper notes along the line of *understanding and editing code with large models*.
- **`/projects`** — coursework and personal projects with repository links.

### 🔐 Private spaces (client-side encryption)

Some content is not meant to be public, but the site is static — so the **encryption happens in the browser**:

- Text and images are encrypted with **AES-256-GCM** before they ever reach the repository; the key is derived locally from a passphrase using **PBKDF2-SHA256 (310,000 iterations)**.
- The repository and the live site hold **only ciphertext**: filenames are randomised, even the manifest is encrypted, and the passphrase never appears in any artifact.
- Decryption happens entirely in the browser; the key never leaves the machine. Without the right passphrase there is not even a single image to fetch.
- Worth being explicit: **the ceiling on this is the strength of the passphrase**. It is built to stop someone casually clicking around, not to resist a targeted offline attack.

### 🎨 Smaller details

- **Homepage guide band** — you land on *what I write / what I'm doing / featured* instead of a wall of posts.
- **Pinned posts** — the theme's native `top` field; higher value sorts first.
- **Sponsors page** — a card wall with self-hosted avatars (no hotlinking).
- **No tracking anywhere** — no analytics, no ads, no third-party cookies.

---

## 📸 Screenshots

<div align="center">
<table>
  <tr>
    <td width="50%" align="center"><img src=".github/assets/screenshots/home.png" alt="Home"><br><sub>Home — guide band and featured posts</sub></td>
    <td width="50%" align="center"><img src=".github/assets/screenshots/posts.png" alt="Posts"><br><sub>Post list</sub></td>
  </tr>
  <tr>
    <td width="50%" align="center"><img src=".github/assets/screenshots/albums.png" alt="Albums"><br><sub>Albums — 27 of them</sub></td>
    <td width="50%" align="center"><img src=".github/assets/screenshots/games.png" alt="Games"><br><sub>Game room — 13 games</sub></td>
  </tr>
  <tr>
    <td width="50%" align="center"><img src=".github/assets/screenshots/research.png" alt="Research"><br><sub>Research</sub></td>
    <td width="50%" align="center"><img src=".github/assets/screenshots/sponsors.png" alt="Sponsors"><br><sub>Sponsors</sub></td>
  </tr>
</table>
</div>

<p align="center">
  <img src=".github/assets/screenshots/mobile-home.png" width="300" alt="Mobile home"><br>
  <sub>Mobile</sub>
</p>

---

## 🧭 Site map

| Path | What it is |
| --- | --- |
| `/` | Home: guide band + featured + post list |
| `/posts/` | Post list (paginated) |
| `/archives/` | Archive |
| `/categories/` · `/tags/` | Categories / tags |
| `/moments/` | Short notes with photos |
| `/projects/` | Project list |
| `/albums/` | Album collection |
| `/research/` | Research |
| `/links/` | Friend links |
| `/sponsors/` | Sponsors |
| `/games/` | Game room |
| `/about/` | About |
| `/private` | Private-space entry (some encrypted spaces are not linked in the nav) |

---

## 🧱 Tech stack

- **[Valaxy](https://github.com/YunYouJun/valaxy)** `1.0.0-rc.15` — a Vite + Vue 3 static blog framework; `valaxy build --ssg` pre-renders the site.
- **[valaxy-theme-yun](https://github.com/YunYouJun/valaxy-theme-yun)** — base theme; 36 components (nav, homepage, sponsors, social links, …) are overridden here.
- **Vue 3 + TypeScript** — all custom components and composables.
- **SCSS** — prose, research, albums and sponsors each get their own file; colours go through theme CSS variables so they follow light/dark automatically.
- **UnoCSS** — atomic classes and icons (Iconify / Remix Icon).
- **Waline** — optional comment backend (off by default here; enabling it needs your own server).
- **Playwright** — used for pre-release acceptance probes in a real browser.

---

## 🚀 Build & deploy

The source project lives in a local workspace; the pipeline looks roughly like this:

```bash
# 1. Build (pre-render to a static site)
rm -rf dist
npx -y pnpm@<version> run build:ssg        # valaxy build --ssg

# 2. Patch the output (feed i18n markers, <head> autodiscovery links)
python fix_dist.py

# 3. Sync to a plain-static copy and add directory-style entries
#    (internal links are extension-less — /posts/foo — while a bare static
#     server only understands /posts/foo/ or /posts/foo.html)
python publish_site.py

# 4. Generate static category / tag listing pages
python gen_taxonomy_entries.py

# 5. Two release gates (both must exit 0)
python privacy_scan.py      <site-dir>   # real name / phone / class / third-party image hosts …
python private_leak_scan.py <site-dir>   # no plaintext from encrypted spaces may leak

# 6. Publish to GitHub Pages (this repository)
python publish_gh.py

# 7. Content-level live audit (HTTP 200 is not enough)
python audit_live.py
```

A few things worth calling out:

- **Nothing ships without passing the gates.** `privacy_scan.py` walks every text file in the output and fails on a real name, phone number, class name or third-party image host; `private_leak_scan.py` makes sure the encrypted spaces left no plaintext behind. Both are "exit code is the verdict".
- **The gates must be given absolute paths.** `os.walk()` on a missing directory does not error — it silently yields zero files, which produces a perfectly clean "all passed". So the scripts validate the target directory up front and print how many files they actually scanned.
- **The final audit runs in a real browser.** Checking only "HTTP 200" misses a whole class of bugs: content that never rendered, hydration mismatches, images that never decoded. Key pages therefore get content-level Playwright assertions — and **no fixed sleeps**, because "download ciphertext, then decrypt locally" flows will always produce false failures on a slow connection.

---

## 📁 Repository layout

```
.
├── .github/assets/            # icon, hero image and screenshots for this README
├── .nojekyll                  # disables Jekyll processing on GitHub Pages
├── index.html                 # homepage (plus 404.html and friends)
├── posts/ · albums/ · …       # directory-style entries for each page (X/index.html)
├── assets/                    # build output: JS / CSS / fonts / images
├── images/                    # site images (avatar, covers, albums)
├── atom.xml · feed.xml        # RSS / Atom
├── sitemap.xml · robots.txt   # sitemap and crawler rules
├── llms.txt · llms-full.txt   # a site summary for LLMs
└── README.md · README.en.md   # what you are reading
```

> ⚠️ Apart from `.github/assets/` and the two READMEs, **everything here is build output** and gets overwritten wholesale on the next release — edits will not survive.

---

## 🤝 Credits

- Framework and theme: [Valaxy](https://github.com/YunYouJun/valaxy) / [valaxy-theme-yun](https://github.com/YunYouJun/valaxy-theme-yun) by [YunYouJun](https://github.com/YunYouJun).
- Icons from [Remix Icon](https://github.com/Remix-Design/RemixIcon) and [Iconify](https://iconify.design/).
- Domain and hosting kindly provided by GitHub Pages.
- And everyone whose name is on the [**sponsors page**](https://sunfleeting-debug.github.io/sponsors/).

## 📄 License

- **Articles and photographs**: all rights reserved. Please do not republish without permission.
- **Code and build output**: this repository exists to serve the site; reading and learning from it is welcome, but please credit the source if you reuse the styling or an implementation idea.
- Third-party resources (framework, theme, icons, fonts) remain under their own licenses.
