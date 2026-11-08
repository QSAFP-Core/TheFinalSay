# thefinalsay.org/press/ — Press & Media Center handoff

## How to upload
Upload the whole `press/` folder to the root of thefinalsay.org so the page lives at **https://thefinalsay.org/press/**.
No existing page was changed. The page uses files that are already on the site (`../cover-en.jpg`, `../cover-zh.jpg`, `../hat-poster.jpg`, `../bwrci-crest.png`, favicons, both free PDFs, `../gift.html`, `../commandments/`).

**Two views**
- `thefinalsay.org/press/` is the public page. Anything not yet supplied is hidden, or shows as a disabled "coming soon" button. No link is ever broken.
- `thefinalsay.org/press/?preview=1` is the review view. Every placeholder appears with an orange dashed outline and a label naming what it is waiting for.

**Turning items on.** Near the top of `index.html` is one settings block, `window.PRESS`. Drop the file into `press/files/`, put its name between the quotes, and the button goes live. For example:
`execSummary: 'files/HUMAN_INTELLIGENCE_Executive_Summary.pdf',`
For sections that hold text (bios, quotes, press releases), replace the bracketed placeholder text and delete the `data-pending="…"` attribute from that element.

---

## B · Placeholders on the page

| Section | Placeholder | Live behaviour until supplied |
|---|---|---|
| Hero | Download Complete Press Kit (`pressKitZip`) | Disabled button marked "coming soon" |
| About the Book | GT Sage's 200–300 word introduction (block `data-editorial="about-intro"`) | Shows interim text assembled verbatim from copy already on thefinalsay.org |
| About the Book | Special Color Edition and further editions | Hidden |
| Authors · MAXBRUCE | Full biography (expandable) | Hidden |
| Authors · MAXBRUCE | Further affiliations (DigiPie International PBC, BWRCI roles) | Hidden. Only "Founder, Temporal Authority Systems PBC" shows, as published on aicomsci.org |
| Authors · GT SAGE | Explanation of the human–AI authorship process | Hidden |
| Talkspresso | Destination link (`talkspresso`) | Disabled button marked "coming soon" |
| Talkspresso | Demo video (`talkspressoVideo`) | "Video coming soon" frame |
| Initiative · HAT | Executive summary PDF (`hatSummary`) | Hidden |
| Initiative · Evidence | Phase I evidence record PDF (`evidenceRecord`) | Hidden |
| Media assets | Official GT Sage portrait; Special Color, Regular Color and B&W edition images; 3D mockups; HAT visual; Talkspresso/Cyberg art | Hidden. No empty cards are shown on the live page |
| Press materials | Exec summary, fact sheet, bios PDF, quotation sheet, EPK ZIP | Hidden |
| Press materials | Press release archive | Hidden |
| Approved quotations | Three quotation slots | **The whole section and its index chip are hidden** until at least one approved quote is entered |

**Interim content to approve**
1. **Short bios.** MAXBRUCE's bio is taken verbatim from the book's back cover. GT Sage's bio is taken verbatim from aicomsci.org. Replace either one if GT writes press versions.
2. **Media email.** No press address exists for thefinalsay.org, so the page uses the existing published address, **briefings@ocup.ai**, set in `mediaEmail`. I recommend creating **press@thefinalsay.org** and changing that one line. The interview, speaking and institutional buttons all open pre-filled emails, so no form, server or credentials are involved.
3. **Media-use notice** (bottom of Media Assets). The wording is drafted and marked "subject to final approval".
4. **GT Sage disclosure.** "AI collaborator operating through OpenAI's ChatGPT … does not imply that OpenAI sponsored, endorsed…". This is adapted from the site's existing attribution footer.

---

## C · Materials still needed

**From GT Sage (text)**
- [ ] About the Book introduction, 200–300 words
- [ ] MAXBRUCE short bio (2–3 sentences), only if different from the back-cover bio
- [ ] MAXBRUCE full biography
- [ ] Confirmed MAXBRUCE affiliations and titles
- [ ] GT Sage press bio and explanation of the human–AI collaboration
- [ ] Approved quotations: exact wording, attribution, source
- [ ] One-page executive summary (PDF)
- [ ] Book fact sheet (PDF): editions, ISBNs, formats, page counts, prices, languages, release dates
- [ ] Author biographies (PDF)
- [ ] Approved quotation sheet (PDF)
- [ ] HAT executive summary (PDF), if it is to be published
- [ ] Phase I evidence record (PDF), if it is to be published separately from the OCUP whitepaper
- [ ] First press release, with date and headline
- [ ] Final media-use wording

**From MAXBRUCE (files and decisions)**
- [ ] Press email address (recommended: press@thefinalsay.org)
- [ ] Talkspresso link and demo video (YouTube/Vimeo link or MP4)
- [ ] Special Color Edition: what it is and where to buy
- [ ] Edition images: Special Color, Regular Color, Black & White (front covers, high-res)
- [ ] 3D book mockups (high-res PNG or JPG)
- [ ] Official GT Sage portrait, if different from the Quorum illustration crop
- [ ] HAT visual and Talkspresso/Cyberg artwork (high-res)
- [ ] Confirmation that the KR260 lab photos may be distributed (these are your own photos; the AMD product render was left out because it is manufacturer imagery)

---

## D · Recommended press kit ZIP structure

```
HUMAN_INTELLIGENCE_Press_Kit/
├── 00_READ_ME_FIRST.pdf                 (contents, credits, media-use terms, contact)
├── 01_Press_Release/
│   └── YYYY-MM-DD_HUMAN_INTELLIGENCE_Press_Release.pdf
├── 02_Executive_Summary_and_Fact_Sheet/
│   ├── HUMAN_INTELLIGENCE_Executive_Summary.pdf
│   └── HUMAN_INTELLIGENCE_Fact_Sheet.pdf
├── 03_Authors/
│   ├── HUMAN_INTELLIGENCE_Author_Biographies.pdf
│   ├── MAXBRUCE_headshot_color.jpg
│   ├── MAXBRUCE_headshot_bw.jpg
│   └── GT_Sage_portrait.png
├── 04_Book_Imagery/
│   ├── HUMAN_INTELLIGENCE_cover_EN.png
│   ├── HUMAN_INTELLIGENCE_cover_ZH.png
│   ├── Special_Color_Edition.png  ·  Regular_Color_Edition.png  ·  BW_Edition.png
│   └── 3D_Mockups/
├── 05_Quorum_and_Talkspresso/
│   ├── Quorum_Plus_One.png
│   └── Talkspresso_Cyberg.png
├── 06_Initiative_and_Research/
│   ├── HAT_Executive_Summary.pdf
│   ├── OCUP_Temporal_Authority_Governance_Whitepaper_v1.5.pdf
│   ├── OCUP_The_Better_AI_Race_Whitepaper.pdf
│   ├── OCUP_authority_boundary_diagram.png
│   └── KR260_Lab_Photos/  (wide, top, ethernet)
├── 07_Approved_Quotations/
│   └── HUMAN_INTELLIGENCE_Approved_Quotations.pdf
└── 08_The_Book/
    ├── HUMAN_INTELLIGENCE_Free_Edition.pdf
    └── HUMAN_INTELLIGENCE_Chinese_Free_Edition.pdf
```
Name it `files/HUMAN_INTELLIGENCE_Press_Kit.zip` and set `pressKitZip` to activate both press kit buttons. Keep it under about 100 MB. If it gets larger, the free-edition PDFs can be left out and linked instead.

---

## E · New files, routes and components

**Route:** `/press/` (new). **No existing pages were changed.**

```
press/
├── index.html                (the page: inline CSS and JS, no dependencies beyond Google Fonts and gtag)
├── files/                    (empty: drop PDFs and the ZIP here)
└── assets/
    ├── press-share.jpg                         1200×630 social share image (og:image)
    ├── maxbruce-headshot-color.jpg / -bw.jpg   2000×2000 originals, plus -web.jpg previews
    ├── gt-sage-portrait.png                    720×720, plus -web.jpg
    ├── quorum-plus-one-heroes.png              1290×3195, plus -web.jpg
    ├── book-cover-en.png / book-cover-zh.png   1200×1800 originals
    ├── ocup-authority-boundary-diagram.png     1344×710, plus -web.jpg
    └── kr260-lab-board-wide / -board-top / -ethernet-closeup .jpg, plus -web.jpg
```

**Components in index.html** (all reuse the site's tokens, fonts, top bar, buttons and footer):
- `window.PRESS` settings block: switches links and files on.
- Pending system (`data-pending` / `data-link` / `?preview=1`): placeholders are hidden on the live page and labelled in preview.
- Sticky section index with scroll highlight.
- Expandable Full Biography, Quorum + One panel (all six members, descriptions from aicomsci.org) and "What Phase I does and does not show".
- Asset cards: web preview, caption, size, and a download of the original file.
- Copy-to-clipboard quotation cards, which copy the exact text with attribution.
- Contact routes that open pre-filled emails; nothing private is exposed.
- Analytics events (same GA4 property G-JFVT7M58F7): `press_download` (item and file), `press_contact` (route), `quote_copy`, `talkspresso_click`, `challenge_click`, `conversations_click`.
- SEO and social: title, description, canonical, Open Graph and Twitter card.

**Suggested small edit to the main site (not made):** add `<li><a href="press/">Press &amp; media</a></li>` to the footer "The book" list on the homepage so journalists can find the page.

---

## Update, Nov 7: GT Sage's EPK working release installed
- `files/` now contains: Executive Summary, Fact Sheet, Author Biographies, Research Brief (HAT · OCUP · KR260), and Talkspresso Overview PDFs, plus `HUMAN_INTELLIGENCE_Press_Kit.zip` (GT's 5.7 MB working release). All are switched on in `window.PRESS`, along with the new `researchBrief` and `talkspressoOverview` entries.
- The **Download Complete Press Kit** button in the hero and the Press Materials tile are now live.
- The author cards use GT's approved short bios. "Full biography" and "How the human–AI authorship worked" open the expanded bios. The affiliation line comes from GT's bio.
- The GT Sage portrait was replaced with the official 1254 × 1254 portrait, and the "official portrait" placeholder was removed.
- The Evidence card and the Press Materials section link the Research Brief. The Talkspresso section has an Overview PDF button.
- Still pending: approved quotations, the dated press release, the About-the-Book introduction, the HAT summary, the edition and mockup images, and the Talkspresso link and video.

## Update, Nov 7 (evening): GT Sage editorial revision installed
- GT's revised `index.html` is now the base page: it adds the About-the-Book introduction, corrects the Temporal Authority Systems PBC ownership wording, and removes the RTL line from the press bio.
- The page bios now match the revised Author Biographies PDF word for word (short and expanded, for both authors).
- The Amazon labels are back to "Full-color hardcover" (B0HNS1PGG2) and "Black & white edition" (B0HQ2F2G98), following the mapping already used in the gift section of thefinalsay.org.
- All five PDFs were rebuilt in the site's visual style: dark title band with gold rule, Cormorant Garamond and Inter type, both covers, and portraits or diagrams where they help. GT's text is unchanged; only headers are set in capitals and the fact sheet is laid out as a table. The build script, `build_press_pdfs.py` (kept in OneDrive beside the press folder, not uploaded), and can be re-run from GT's source PDFs.
- The EPK ZIP was repacked with the restyled PDFs, keeping GT's folder structure and read-me.
