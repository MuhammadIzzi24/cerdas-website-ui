# CERDAS Website — UI Prototype

A clickable design prototype for the **Centre for Resilient Data Analytics and Computational Systems (CERDAS)**, Universiti Teknologi PETRONAS.

This is a **prototype, not the live website**. There is no database, no login, no content management system, and nothing here is published to the public internet. It exists so we can look at the design, click through it, and agree on how the real site should work before anyone builds it for real.

> **Everything you read on these pages is placeholder text.** Every name, number, publication and partner is invented. Before anything goes live it must be replaced with real, verified content — see [REPLACE-LIST.md](REPLACE-LIST.md), which tracks every placeholder page by page.

---

## Getting started

You don't need Node, npm, or any build step — just Python, a browser, and an internet connection (the pages load their fonts and a small script library online).

### Step 1 — Check you have Python

Open a terminal (Windows: press the Start key, type `terminal`, press Enter) and run:

```bash
python --version
```

If it prints something like `Python 3.12.4`, you're set — skip to Step 2.

If it says the command isn't found, **or the Microsoft Store opens instead**, install Python from [python.org/downloads](https://www.python.org/downloads/). On the first screen of the installer, **tick "Add python.exe to PATH"** before clicking Install — this is the step people miss. Then close and reopen your terminal and try `python --version` again.

> On Mac, use `python3` instead of `python` in every command in this README.

### Step 2 — Get the files

Pick **one** of these.

**Option A — Clone with Git (recommended).** You'll be able to pull updates and push your changes. Check you have Git with `git --version`; if not, install it from [git-scm.com](https://git-scm.com/downloads) with the default options. Then:

```bash
cd Documents
git clone https://github.com/MuhammadIzzi24/cerdas-website-ui.git
cd cerdas-website-ui
```

This creates a `cerdas-website-ui` folder inside Documents and moves your terminal into it.

**Option B — Download a ZIP.** Quicker if you only want to look. On the [repository page](https://github.com/MuhammadIzzi24/cerdas-website-ui), click the green **Code** button → **Download ZIP**. Right-click the downloaded file → **Extract All**. You'll get a folder called `cerdas-website-ui-main`. Note that a ZIP is a one-off copy — it won't receive updates, and you can't push changes from it.

### Step 3 — Open a terminal inside the folder

If you cloned in Step 2, your terminal is already there — skip ahead.

Otherwise, open the folder in File Explorer, **right-click an empty space** inside it, and choose **Open in Terminal**. (Alternative: click the address bar at the top of File Explorer, type `cmd`, press Enter.)

To check you're in the right place, run `dir` (Mac: `ls`). You should see `README.md` and a long list of `CERDAS ... .dc.html` files. If you don't, you're in the wrong folder.

### Step 4 — Start the local server

```bash
python -m http.server 8000
```

You should see `Serving HTTP on :: port 8000 ...`. **Leave this terminal window open** — closing it stops the website. If Windows asks about firewall access, click **Allow** (or Cancel — it only affects other computers reaching yours, not you).

### Step 5 — Open the site in your browser

Go to:

```
http://localhost:8000/CERDAS%20Home.dc.html
```

Give it a couple of seconds on first load. From the home page you can click through to every other page, the same way a visitor would. `http://localhost:8000` on its own shows a plain list of every file, which is handy for jumping straight to a component or a mobile page.

### Step 6 — Stop the server when you're done

Click into the terminal and press `Ctrl+C`. Next time, just repeat Steps 3 to 5 — you don't need to download anything again.

### If something goes wrong

| Problem | Fix |
|---|---|
| **Page loads but has no header, footer, or looks broken** | You opened the file directly (the address bar starts with `file:///`). Browsers block pages from loading other local files, so the shared header and footer fail silently. Always use `http://localhost:8000/...` — never double-click the `.html` files. |
| **Page stays blank** | Check your internet connection — the pages load a script library and fonts online. Then hard-refresh with `Ctrl+Shift+R`. |
| **"This site can't be reached"** | The server isn't running. Check the terminal from Step 4 is still open and didn't show an error. |
| **Error mentioning `address already in use`** | Something else is using port 8000. Use another number — `python -m http.server 8080` — and change `8000` to `8080` in the browser address too. |
| **"Error code: 404 — File not found"** | The server was started in the wrong folder. Stop it with `Ctrl+C`, go back to Step 3, and check with `dir` before starting it again. |
| **Your edits don't show up** | Save the file, then hard-refresh with `Ctrl+Shift+R`. |

---

## What's in this folder

| | |
|---|---|
| **`CERDAS *.dc.html`** | The pages. One file per screen — Home, Research, People, Projects, Governance, and so on. These are what you'll spend your time editing. |
| **`SiteHeader`, `PersonCard`, `ProjectCard`, …`.dc.html`** | Reusable components. Small pieces that get pulled into many pages at once. See below. |
| **`support.js`, `image-slot.js`** | The engine that makes components and image placeholders work. **Never edit these** — they are generated files and your changes would be wiped out. |
| **`assets/`** | Real CERDAS logos. |
| **`uploads/`** | Source material the design was built from — the written spec, reference images. |
| **`REPLACE-LIST.md`** | The master checklist of every invented value that needs replacing before launch. |

Files starting with `CERDAS Mobile *` are the phone versions of key screens. `CERDAS Theme.dc.html` is the style reference sheet — colours, fonts and components shown all in one place. It's the best page to look at first.

---

## How a page is built

Good news: it's **plain HTML with inline styles**. No React, no Tailwind, no framework to learn. If you can read HTML and CSS, you can edit these pages.

Two things are unusual, and they're both worth understanding.

### 1. Components — `dc-import`

Instead of copy-pasting the site header into all 30 pages, each page says:

```html
<dc-import name="SiteHeader" active="Home"></dc-import>
```

That pulls in `SiteHeader.dc.html` when the page loads. The extra attributes (`active="Home"`) are **props** — settings passed into the component.

This means: **edit `SiteHeader.dc.html` once, and every page updates.** That's the whole point. If you find yourself making the same change on ten pages, stop — you're probably editing something that should be a component.

### 2. Placeholders — `{{ }}`

Inside a component file, double curly braces mark where a prop gets slotted in. From `ThemeChip.dc.html`:

```html
<span style="...">{{ label }}</span>
```

So `<dc-import name="ThemeChip" label="Machine Learning"></dc-import>` renders a chip reading "Machine Learning".

---

## Making your first edit

1. Start the server and find the page in your browser.
2. Open the matching `.dc.html` file in your editor.
3. Use `Ctrl+F` to search for the text you saw on screen — the file is in roughly the same order as the page.
4. Change it, save, and refresh the browser.

That's it. There's no build step and nothing to recompile.

If you edited a `.dc.html` component and nothing changed on screen, do a hard refresh (`Ctrl+Shift+R`) — the browser caches these.

---

## House style

Please stick to the existing palette and fonts. The design is deliberately restrained, and new colours show up immediately.

**Colours**

| | |
|---|---|
| `#004B8C` | UTP blue — primary, links, buttons |
| `#00335F` | Darker blue — hover state |
| `#E38C07` | Orange — accents and markers only, used sparingly |
| `#14181D` | Near-black — headings and body text |
| `#5A6472` | Grey — secondary and supporting text |
| `#FFFFFF` / `#FAFAF8` | Page backgrounds |
| `#D8DEE5` | Borders and rules |
| `#E6EEF5` / `#F2F6FA` | Pale blue fills — chips, highlighted panels |

**Fonts** — `Inter Tight` for headings, `Inter` for body text, `IBM Plex Mono` for statistics, labels and anything in small caps. All three load automatically from Google Fonts.

**Layout** — desktop pages are `1440px` wide with content in a `1320px` column. Keep those numbers unless you're intentionally redesigning a section.

---

## Working with Git

Save your work to GitHub regularly — at minimum at the end of each day, ideally after each meaningful change.

```bash
git add -A && git commit -m "Update People page bios" && git push
```

Write commit messages that say **what changed**, so `Fix Governance page committee table`, not `update` or `changes`.

Before you start work each day, pull down anything that changed:

```bash
git pull
```

If Git reports a conflict and you're not sure what to do, **stop and ask** rather than guessing. Nothing is ever really lost in Git, but untangling it is much easier before more changes pile on top.

---

## Things to be careful about

**Don't invent content.** If you need a name, a number or a publication and don't have a real one, leave the placeholder alone and add a row to `REPLACE-LIST.md`. An invented statistic that quietly survives to launch is the single most damaging thing that can happen to this project.

**Don't edit `support.js` or `image-slot.js`.** They're generated.

**Check the mobile pages too.** If you change the header, footer or navigation, the `CERDAS Mobile *` files often need the same change — they're separate files, not automatic.

**Ask early.** If something looks wrong or you're unsure whether a change is wanted, ask before doing it across thirty pages.
