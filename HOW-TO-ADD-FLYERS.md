# How to Add Flyers & Updates — Miguel's Quick Guide

Your site reads everything from **flyers.json**. There are TWO kinds of cards:

1. **PDF flyer** — a card that opens a PDF (the flyer library)
2. **Info post / Update** — a card that EXPANDS INLINE and lives in the
   **"Updates & Insights"** section (rate moves, guideline changes, strategy
   explainers — no PDF needed)

Live site: https://miguelpinatx.github.io/partner-toolkit/

---

## 📄 To add a PDF FLYER (3 steps)

1. **Name the PDF** lowercase-with-dashes: `va-jumbo-loans.pdf`
2. **Upload it** to the `flyers` folder (Add file → Upload files → Commit)
3. **Add this to flyers.json** (inside the `"flyers": [ ]` list):

```json
    {
      "type": "pdf",
      "slug": "va-jumbo-loans",
      "title": "VA Jumbo Loans",
      "category": "Investor & Specialty",
      "blurb": "One or two sentences describing the flyer.",
      "use_when": "A short cue for when to reach for it."
    },
```

`slug` must match the PDF filename without `.pdf`.

---

## 📰 To add an UPDATE / INFO POST (no PDF)

**This is the one where you send me the raw info and I write it up.**

These show up in the **"Updates & Insights"** section, newest first. Great for
rate moves, guideline changes, or explainers like "buying a home for an elderly
parent."

Send me an article, a rate bulletin, a guideline change — whatever — and I'll
hand back a ready-to-paste entry like this:

```json
    {
      "type": "info",
      "slug": "fed-rate-update",
      "title": "Fed Holds Rates — What It Means for Buyers",
      "category": "Market & Education",
      "blurb": "Short teaser shown on the card before it's opened.",
      "use_when": "A buyer asks \"should I wait for rates to drop?\"",
      "posted": "2026-06-25",
      "date": "June 2026",
      "highlights": [
        "First key point in plain English.",
        "Second key point.",
        "Third key point."
      ],
      "footer_note": "Optional disclaimer, e.g. 'Not a rate prediction.'"
    },
```

Then: open **flyers.json** → paste the entry → **Commit**. It appears in
Updates & Insights and expands inline when tapped.

**Fields that matter for updates:**
- `type`: must be `"info"`
- `posted`: real date as `YYYY-MM-DD` — this sets the NEWEST-FIRST order
- `date`: the friendly label shown on the card (e.g. "June 2026")
- `highlights`: the bullet points
- `footer_note`: optional compliance/CTA line
- `category`: still required, but info posts always live in Updates & Insights
  regardless — just use any of the four valid names.

**To put a post at the top:** give it the most recent `posted` date.

---

## ✏️ Updating & removing

- **New version of a PDF:** upload it with the same filename. Done.
- **Edit any card's text:** edit its entry in flyers.json.
- **Remove a card/post:** delete its entry from flyers.json (and the PDF if it had one).

---

## ⚠️ Gotchas

- **Commas matter.** Every entry needs a comma after its `}` except the LAST one
  in the list. A stray/missing comma is the #1 cause of "Flyers are loading…"
  that never finishes. GitHub usually underlines the mistake when you edit.
- **category must be exact**, one of:
  `Quick Reference`, `Buyer Programs`, `Investor & Specialty`, `Market & Education`
- **Quotes inside text:** put a backslash before them: `\"like this\"`.
  (When I write posts for you, I handle this.)
- A brand-new 5th flyer category still needs me.

---

## Files

- `index.html` ............ the live toolkit (reads flyers.json)
- `flyers.json` ........... your editable list (PDF flyers + updates)
- `flyers/` .............. the PDF files
- `austin-home-team.html` . the Austin Home Team co-branded version
- `assets/` .............. logo files
