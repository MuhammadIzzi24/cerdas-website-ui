# CERDAS Website — UI Prototype

A clickable design prototype for the **Centre for Resilient Data Analytics and Computational Systems (CERDAS)**, Universiti Teknologi PETRONAS.

This is a **prototype, not the live website**. There is no database, no login, no content management system, and nothing here is published to the public internet. It exists so we can look at the design, click through it, and agree on how the real site should work before anyone builds it for real.

> **Everything you read on these pages is placeholder text.** Every name, number, publication and partner is invented. Before anything goes live it must be replaced with real, verified content — see [REPLACE-LIST.md](REPLACE-LIST.md), which tracks every placeholder page by page.

---

## Getting started

You need **Python** installed (check by running `python --version`). You don't need Node, npm, or any build step.

Open a terminal **in this folder** and run:

```bash
python -m http.server 8000
```

Leave that running, then open this in your browser:

```
http://localhost:8000/CERDAS%20Home.dc.html
```

From the home page you can click through to every other page, the same way a visitor would.

**Don't just double-click the `.html` files.** They will open, but the shared header and footer won't load and the page will look broken. This is a browser security rule about local files, not a bug. Always go through `http://localhost:8000`.

When you're finished, press `Ctrl+C` in the terminal to stop the server.

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
