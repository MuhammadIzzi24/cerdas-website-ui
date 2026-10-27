# CERDAS Website — UI Prototype

A clickable design prototype for the **Centre for Resilient Data Analytics and Computational Systems (CERDAS)**, Universiti Teknologi PETRONAS.

This is a **prototype, not the live website**. There is no database, no login and no content management system. It exists so we can look at the design, click through it, and agree on how the real site should work before anyone builds it for real.

> **Content is a mix of real and placeholder.** Researcher names, departments, emails, tiers, research groups and photos, the organisation chart, the six research groups (RG01–RG06) and the inventions & products list come from CERDAS's own files in `uploads/`. Anything that can't be traced to a file in `uploads/` is still a placeholder and must be verified before launch. See [REPLACE-LIST.md](REPLACE-LIST.md) and `Step 2 - Change log.md`.

---

## Getting started

You don't need Node, npm, or any build step — just Python, a browser, and an internet connection (the pages load their fonts and a small script library online).

### Step 1 — Check you have Python

Open a terminal (Windows: press the Start key, type `terminal`, press Enter) and run:

```
python --version
```

If it prints something like `Python 3.12.4`, you're set — skip to Step 2.

If it says the command isn't found, **or the Microsoft Store opens instead**, install Python from [python.org/downloads](https://www.python.org/downloads/). On the first screen of the installer, **tick "Add python.exe to PATH"** before clicking Install. Then close and reopen your terminal and try again.

> On Mac, use `python3` instead of `python` in every command in this README.

### Step 2 — Get the files

**Option A — Clone with Git (recommended).** You'll be able to pull updates and push your changes. Check you have Git with `git --version`; if not, install it from [git-scm.com](https://git-scm.com/downloads). Then:

```
cd Documents
git clone https://github.com/MuhammadIzzi24/cerdas-website-ui.git
cd cerdas-website-ui
```

**Option B — Download a ZIP.** On the repository page, click **Code → Download ZIP**, then right-click the file → **Extract All**. A ZIP is a one-off copy — it won't receive updates, and you can't push changes from it.

### Step 3 — Open a terminal inside the folder

If you cloned in Step 2, your terminal is already there. Otherwise, open the folder in File Explorer, right-click an empty space and choose **Open in Terminal**.

Run `dir` (Mac: `ls`). You should see `README.md` and a list of `CERDAS ... .dc.html` files.

### Step 4 — Start the local server

```
python -m http.server 8000
```

**Leave this terminal window open** — closing it stops the website.

### Step 5 — Open the site in your browser

```
http://localhost:8000/CERDAS%20Home.dc.html
```

From the home page you can click through to every other page. `http://localhost:8000` on its own lists every file.

### Step 6 — Stop the server

Press `Ctrl+C` in the terminal.

### If something goes wrong

| Problem | Fix |
|---|---|
| **No header or footer, or the page looks broken** | You opened the file directly (`file:///`). Always use `http://localhost:8000/...`. |
| **Page stays blank** | Check your internet connection, then hard-refresh with `Ctrl+Shift+R`. |
| **"This site can't be reached"** | The server isn't running — check the terminal from Step 4. |
| **`address already in use`** | Use another port: `python -m http.server 8080`, and change the address to match. |
| **"404 — File not found"** | The server was started in the wrong folder. Stop it, go back to Step 3. |
| **Your edits don't show up** | Save, then hard-refresh with `Ctrl+Shift+R`. |

---

## What's in this folder

| | |
|---|---|
| **`CERDAS *.dc.html`** | The pages — Home, Our Vision, Organisation Chart, Fellowship Framework, Research, People, Researcher Profile, Projects, Facilities, Inventions and Products, Publications, News and Events, Join, and so on. |
| **`SiteHeader`, `PersonCard`, `ProjectCard`, …`.dc.html`** | Reusable components pulled into many pages at once. |
| **`SA-*.dc.html`** | Self-contained versions of the shared components, used by the standalone files. |
| **`CERDAS Home v1`, `CERDAS Home Variations*`** | Earlier Home page designs, kept for reference. |
| **`support.js`, `image-slot.js`** | The engine that makes components and image slots work. **Never edit these.** |
| **`.image-slots.state.json`** | Saved photo positions for image slots. Keep it alongside the pages. |
| **`assets/`** | Logos, banner photos, researcher photos, facilities, news and partner images. |
| **`data/`** | Researcher, invention and industry-project data imported from the Excel files. |
| **`uploads/`** | Source material — the spec, Excel lists, org charts, photos. |
| **`extracted/`** | Plain-text extracts of the spec and org charts. |
| **`REPLACE-LIST.md`** | Checklist of placeholder values still to verify before launch. |
| **`Step 1 - Excel import plan.md`, `Step 2 - Change log.md`** | What was changed when the Excel data was imported. |

Files starting with `CERDAS Mobile *` are the phone versions of key screens. `CERDAS Theme.dc.html` is the style reference sheet.

---

## How a page is built

It's **plain HTML with inline styles** — no framework to learn.

### 1. Components — `dc-import`

```html
<dc-import name="SiteHeader" active="Home"></dc-import>
```

That pulls in `SiteHeader.dc.html` when the page loads. `active="Home"` is a **prop** — a setting passed into the component. **Edit `SiteHeader.dc.html` once, and every page updates.**

### 2. Placeholders — `{{ }}`

Inside a component, double curly braces mark where a prop is slotted in:

```html
<span style="...">{{ label }}</span>
```

---

## Making an edit

1. Start the server and find the page in your browser.
2. Open the matching `.dc.html` file in your editor.
3. `Ctrl+F` for the text you saw on screen.
4. Change it, save, and refresh.

---

## House style

**Colours**

| | |
|---|---|
| `#004B8C` | UTP blue — primary, links, buttons |
| `#00335F` | Darker blue — hover state |
| `#E38C07` | Orange — accents only, used sparingly |
| `#14181D` | Near-black — headings and body text |
| `#5A6472` | Grey — secondary text |
| `#FFFFFF` / `#FAFAF8` | Page backgrounds |
| `#D8DEE5` | Borders and rules |
| `#E6EEF5` / `#F2F6FA` | Pale blue fills |

**Fonts** — `Inter Tight` for headings, `Inter` for body, `IBM Plex Mono` for statistics and labels.

**Layout** — desktop pages are `1440px` wide with a `1320px` content column. Page banners (except Home) are `500px` tall with a dark photo overlay and white text.

---

## Working with Git

```
git pull
git add -A && git commit -m "Update People page bios" && git push
```

Write commit messages that say **what changed**. If Git reports a conflict and you're not sure what to do, **stop and ask**.

---

## Things to be careful about

**Don't invent content.** If you need a name, number or publication and don't have a real one, leave the placeholder and add a row to `REPLACE-LIST.md`.

**This repository is public.** It contains real researcher names, emails and photos — make sure that's approved, or make the repository private.

**Check the mobile pages too.** Header, footer and navigation changes usually need the same change in the `CERDAS Mobile *` files.
