# Step 1 — Plan: people & inventions from "All List of PI CERDAS.xlsx"

Source: sheet **List of Product@Invention** only. Nothing has been edited yet.

---

## a) Counts

| | Expected | Counted |
|---|---|---|
| Rows (2–89) | 88 | **88** |
| Researchers | 33 | **33** |
| …with ≥1 invention | 19 | **19** |
| …with none ("-") | 14 | **14** |
| Invention rows | — | **74** (88 − 14) |
| Distinct inventions (unique Title) | 49 | **49** — 36 have one listed inventor, 13 are shared (38 rows) |
| Inventions with a real product name | — | **20** |
| Distinct product names | — | **18** (DataESC is the product of 3 inventions) |

**Why "Total" says 63:** 88 rows − 25 repeat rows of shared inventions = 63. In other words it counts the 14 "no invention" rows as projects (49 + 14 = 63). Its "38 occurrences" = the 38 rows that belong to the 13 shared inventions. It will not be used anywhere.

**Note:** 19 of the 49 inventions have **no Main Inventor** in the list (only Co-Inventor / Custodian rows) — e.g. all 5 of Aliza Sarlan's are "Custodian". I will show only the people and roles the Excel lists.

Inventions per researcher: Izzatdin 13 · Jafreezal 10 · Hanita 9 · Mohd Hilmi 7 · Aliza 5 · Yew Kwang Hooi 5 · Emelia 4 · Ahmad Bukhari 3 · Mohd Fadzil 3 · Said Jadid 3 · Hamzah 2 · Nurul Aida 2 · Shuhaida 2 · Dennis 1 · Hitham 1 · Mohana 1 · Anuaruddin 1 · Nooraini 1 · Farahida 1.

---

## b + c) Pages and components, and what changes

### 1. Researcher listing — rebuilt from the Excel
**CERDAS People.dc.html** and **CERDAS Mobile People.dc.html**
- Replace: 33 cards → Name · Department (as written) · Email. Researcher count = 33 (now sourced from the Excel).
- Remove: photo slot, academic titles, tier sections (Principal / Senior / Researcher + their counts), role (Group Head / Member), research group, expertise chips; stats "3 Principal", "9 Senior", "6 Research groups"; role / group / expertise filters; sidebar group counts and "Looking for expertise in…" cloud; "…across six research groups" result line.
- Waiting on you: Leadership row (Director + Centre Research Officer), hero sentence, other sidebar boxes, search box (Q4–Q5).

**PersonCard, SA-PersonCard, PersonCardFeatured, SA-PersonCardFeatured**
- Become Name · Department · Email (mailto). Photo, title prefix, role, tier, research group, chips and the "Publications" icon removed. Profile arrow only where a profile page exists (Hitham).
- Sample default preview names (Aminah Zainuddin, Rashid Anuar) → first researcher in the Excel.

### 2. Profile pages (only one exists: Hitham)
**CERDAS Researcher Profile.dc.html** and **CERDAS Mobile Profile.dc.html**
- Name → "Hitham Seddig Alhassan Alhussian" (no title). Department → "Computing" (now "Department of Computer & Information Sciences, Universiti Teknologi PETRONAS"). Email already matches (seddig.alhussian@utp.edu.my).
- New **Inventions** tab (same style as the other tabs): 1 invention — *Intelligent Constructability Review (i-CR)*, Co-Inventor (with Yew Kwang Hooi, Main Inventor; Said Jadid Abdulkadir, Co-Inventor).
- Waiting on you (Q9): tier badge, "Group Head" role, one-liner, ORCID/Scopus/Scholar, supervision availability, Biography, Research interests, Publications, Projects, Supervision, Teaching, Awards, metrics, expertise, theme box, "Others in this theme", "Work with Dr. Hitham", "Profile updated 12 Aug 2026".

### 3. Patents → Inventions & Products
**CERDAS Patents.dc.html** → renamed **CERDAS Inventions and Products.dc.html** (title, breadcrumb, h1), all links updated.
- Show all 49 once: Title · Product (20 have one) · Inventors with role · Description (clamped, "Read more"). Excel order.
- Remove: jurisdiction, numbers, filing dates, status badges, "Available to license", group/project tags, "Abstract →" and "Licensing enquiry →" links, "8 of 19 shown / Updated 28 Aug 2026", "Load the remaining 11 filings", "Where we file" (19/4/3/2), hero sentence about filing/jurisdictions, all 8 sample patents and their inventors.
- Numbers band (3 counters): 49 inventions · 19 researchers with an invention · 20 (or 18) named products (Q7).
- Waiting on you (Q8): "License a CERDAS technology" panel (Emelia as named contact) and the three IP-policy notes.
- Menu label "Patents" → "Inventions & Products" in: SiteHeader, SA-SiteHeader, MobileDrawer, SiteFooter, SA-SiteFooter, MobileFooter, Sitemap card (its "Filings and grants by jurisdiction" line removed), Publications sidebar link. There is no mobile Patents page — mobile menus already open the desktop page; that stays.

### 4. Pages that show researcher names from the org chart (not the Excel) — unchanged unless Q2 says otherwise
- **CERDAS Organisation Chart** — all 33 names with titles, group membership, functional leads, Director, CRO.
- **CERDAS Research** — six group heads, per-group counts.
- **CERDAS Theme**, **CERDAS Theme -standalone src-**, **CERDAS Research Group (standalone).html** — members with titles, roles, tiers, expertise chips.
- Contact boxes: Patents (Emelia), Technology Transfer (Emelia; Yew Kwang Hooi), Industry (Yew Kwang Hooi), Join (Shuhaida; Yew Kwang Hooi; Latty), News Article (Latty).

### 5. Not touched
CERDAS Consultancy (your rule 6); Projects page + desktop Home flagships (PIs come from your consultancy Excel — not sample); Home Variations archive (frozen); REPLACE-LIST.md (internal notes).

---

## d) Names on the site that are NOT in the Excel

**Probably real staff**
- **Latty Shazana Ismail** — People (leadership card), Mobile People, Organisation Chart (CRO), Join (2 contact boxes), News Article (media enquiries).

**Invented / sample people**
- Ir. Faizal Ramli — News Article (quote).
- Prof. Dr. Lim Wei Sheng, Dr. Siti Noor Azmi, Assoc. Prof. Dr. Faridah Sulaiman — News & Events (event speakers).
- Amirul Hakim bin Roslan, Chen Xiao Wen, Priyanka Nair, Muhammad Danial bin Zulkarnain, Lee Su Ann, Nur Alia binti Kamarudin — Researcher Profile + Mobile Profile (students); Amirul also on Project Detail.
- Faridah Sulaiman — Researcher Profile + Mobile Profile (project text).
- Citation-style authors/inventors:
  - Patents: Iskandar S., Rahim A. N., Noor Azmi S., Bakri A., Tengku Zainal M. F., Ooi L. W., Kamal N. I., Zainuddin A., Zulkifli I., Lim W. S., Tan C. M., Sulaiman F., Idris W. S., Hamzah N., Suresh R., Amri K.
  - Publications: all of the above + Verma P., Haryono D., Devaraj K., Whitfield J. R., Perera S., Okafor E., Ramachandran T., Nwosu C., Bianchi L.
  - Home, Home v1, Home Variations, Mobile Home: Iskandar, Rahim, Verma, Tengku Zainal, Ooi, Haryono, Devaraj, Noor Azmi, Whitfield.
  - Researcher Profile + Mobile Profile: Nwosu C., Perera S., Devaraj K.
  - PublicationRow default: Iskandar, Rahim, Verma.
- Component defaults: PersonCard / SA-PersonCard "Prof. Dr. Aminah Zainuddin"; PersonCardFeatured / SA-PersonCardFeatured "Prof. Ts. Dr. Rashid Anuar".

**In the Excel but spelled differently on the site**
- Noureen **Talpur** (site, and her Excel email) vs **Talphur** (Excel name)
- Emelia Akashah Patah Akhir vs Emelia Akashah **Bt** Patah Akhir
- Maged **Mohamed** Saeed Nasser vs Maged **Mohammed** Saeed Nasser
- Mohana Sundaram **A/L** Muthuvalu vs Mohana Sundaram Muthuvalu
- Ahmad Bukhari Aujih vs Ahmad Bukhari **bin** Aujih
- Every name on the site carries academic titles (Prof. / Assoc. Prof. / Dr. / Ts.) — the Excel has none.

---

## e) Sample items that show a real researcher's name (rule 4)

- **Researcher Profile + Mobile Profile (Hitham)** — 5 sample publications (co-authors Talpur N., Zainuddin N., Daud H.); 5 sample projects (SENTINEL-GRID, CLARA, AQUA-SENSE, GRID-OBS, LOADSHAPE); Supervision "completed" lists **Dr. Hanita Daud, Ts. Dr. Yaman Hamed, Dr. Aliza Sarlan** as his former students with invented destinations; "Others in this theme" (Said Jadid shown as Principal Researcher, Hanita Daud, Noureen Talpur, Aliza Sarlan) with invented focus lines; invented bio, career, teaching, awards.
- **Project Detail** (sample SENTINEL-GRID) — PI Hitham; team Hanita Daud, Aliza Sarlan, Said Jadid Abdulkadir, Emelia Akashah Patah Akhir.
- **Home v1, Home Variations, Mobile Home** — sample flagship "SIGMA-Flow" with PI Izzatdin Abdul Aziz.
- **Theme pages** — 8 sample projects with PIs: SENTINEL-Grid (Said Jadid), CLARA (Noureen), LATCH (Ahmad Bukhari), SIGMA-Flow (Mohana), MESH-Opt (Hamzah), EDGE-Sense (Anuaruddin), QOPT (Ibrahim), FLUX (Mohd Fadzil); sample publications authored by ~25 researchers; sample facilities with "Lead" (Hitham, Said Jadid, Shakirah, Mohana, Anuaruddin, Ahmad Bukhari, Ibrahim).
- **Publications** — sample paper "Sparse graph learning for fault localisation…" lists Daud, H.
- **Patents** — sample patent "Graph-based fault localisation apparatus…" lists Daud, H. (removed in Step 2 anyway).
- **Datasets** — 6 sample datasets, contacts: Siti Nurlaili Karim, Hitham, Hamzah Sakidin, Noureen Talpur, Ahmad Bukhari Aujih, Ibrahim Venkat Krishnamurthy.
- **Software** — 6 sample packages, maintainers: Siti Nurlaili Karim, Hamzah Sakidin, Hitham, Ahmad Bukhari Aujih, Ibrahim Venkat Krishnamurthy, Nur Syadhila Che Lah.
- **Join** — sample openings with owners: scholarships (Siti Nurlaili, Hitham, Shakirah, Ibrahim, Mohana, Ahmad Bukhari); postdoc (Mohana, Anuaruddin); positions (Hamzah, Hitham, Nur Syadhila); internships (Noureen, Ahmad Bukhari, Rajalingam, Mohd Fadzil, Nur Syadhila); collaborate challenges (Mohana ×2, Anuaruddin, Ibrahim).
- **News Article** (sample Selat Energy story) — quote attributed to Hitham, plus a "Researcher" link to him.
- **Facility Detail** (sample PETRA-1 HPC) — facility manager Nur Syadhila Che Lah.
- **Component defaults** — FacilityCard / SA-FacilityCard lead "Said Jadid Abdulkadir"; ProjectCard / SA-ProjectCard PI "Shakirah Mohd Taib".

---

## f) People / patent numbers the Excel cannot support

- **People + Mobile People** — 3 Principal, 9 Senior, 21 Researchers (tier totals); 6 research groups; sidebar group counts; "six research groups", "three-tier". (33 researchers = Excel ✓)
- **Patents** — 19 filed 2021–2025, 7 granted, 4 jurisdictions, 12 proof-of-concepts; 8 of 19 shown; remaining 11; Where we file 19 / 4 / 3 / 2; "within four weeks".
- **Profile + Mobile Profile** — tab counts 4 / 68 / 5 / 23 / 4 / 6; metrics 68 publications, 2,140 citations, h-index 24, 23 students, 3 active projects, RM 4.2M grants; "All 68 in the register"; "Nine current… fourteen completed"; "Three active and two completed"; "6 researchers, 11 active projects"; class sizes 186 / 41 / 34 / 22; "Two funded PhD places".
- **Home** — 19 patents filed. **Home v1** — 19 patents filed, per-group 6 / 5 / 4 / 7, "14 papers · 2 patents". **Home Variations** — 68 researchers, 19 patents, T1–T4 24 / 17 / 15 / 12. **Mobile Home** — T1–T4 24 / 17 / 15 / 12.
- **Projects** — 19 patents filed.
- **Research** — per-group researcher counts 6 / 5 / 4 / 7 / 6 / 5 (33 total ✓).
- **Theme** — sub-area counts (3 / 2 / 1 researchers), "One more researcher sits in this group".
- **Research Dashboard + Mobile Dashboard** — "19 filed 2021–2025 · 7 granted · 12 proof-of-concepts".
- **Fellowship Framework** — 68 current appointments; per-type "N people" (8, 15, 45, 6, 9, 7, 60, 28, 11).
- **Partnerships** — 21 visiting researchers.
- **Technology Transfer** — 14 technologies at TRL 6+, 6 licences, RM 2.8M licensing income, 2 spin-offs.
- **News & Events / News Article** — "Two patents granted…", "Twelve postgraduate researchers complete…".
- **Industry** — "one patent filing under examination in the United States".
- **Project Detail** — "MY-196072, granted · available to license"; "four postgraduate researchers and one research officer".

---

## g) Department values that look like positions

| Researcher | "Department" in Excel |
|---|---|
| Aliza Sarlan | Dean CFS |
| Izzatdin Abdul Aziz | Institute Director |
| Jafreezal Jaafar | Dean FSMC (site/org chart: CERDAS Director) |
| Mohd Fadzil Hassan | Dean PGR |
| Mohd Hilmi Hasan | Chair Computing |

The rest: Computing (19), Applied Science (8), Electrical & Electronics Engineering (1).

---

## h) Data issues (listed, not fixed)

**Differences between inventors' rows of the same invention:** none in title, product or description wording. Only *Simpler UNBab hydrostatics…* has product "-" on Hamzah's row and blank on Nooraini's (both = no product).

**Possible duplicates / related — shown separately (49) unless you say otherwise**
- "System And Method For Productivity Analysis" (product: Productivity Nominal Analytics (PNA)) and a separate invention titled "Productivity Nominal Analytics (PNA)" — both Ahmad Bukhari, different descriptions.
- "Development of a Mobile Application Using Augmentative and Alternative Communication…" and "Autism Made Easy - Pseudocode & source code" — identical descriptions.
- "DOMAIN System Architecture" and "DOMAIN Modelling Framework" — identical descriptions, same four inventors (different Main Inventor).
- Three DataESC inventions (hiding / detecting & correcting / compressing data) share one product name.

**Typos and inconsistencies**
- Titles: "Appratus" (2 DataESC titles; the third says "Apparatus"); "Meteorlogical"; "Process Hazards Managements"; "Mathaid" vs product "MathAid"; "IR 5.0 Transformation Alliances (IR-ACE)" vs description "Alliance (IR-Ace)"; "Auto-P" (title) vs "AutoP" (product); 2 titles end with a full stop; 4 titles have double or trailing spaces (I will only trim spaces).
- Products: "Vrtualize" vs "VRtualize" in its description; "AuPReS" vs "AuPRES"; "HD-Sim" vs "D-Sim".
- Descriptions: "appratus", "errorr"; "perameters"; "Embodiesments"; stray "ä" at the start of "ä system…" (AALDS); "Swam Intelligence"; "U-Metrix", "non-liner"; "LFlEs" (l for I), stray "Open" before "v)", "GaussSeidel"; "time-ofuse"; "proces of hazard"; "assesment"; "the important of road safety"; "lie Tsunamis' height" (probably "i."); acronym "HTEWS" for "Hybrid Tsunami Warning System"; two descriptions start in lower case.
- People: "Noureen Talphur" but email noureen.talpur@utp.edu.my; Hamzah Sakidin's email has a trailing space (will trim); Shakirah Mohd Taib's email is "shakita@utp.edu.my" — please confirm.
