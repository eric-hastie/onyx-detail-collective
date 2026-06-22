# Marketing — Leave-Behind & Before/After Sheet

Two print-ready, Onyx-branded handouts for walk-ups and follow-ups.

| File | What it is | Use it for |
|---|---|---|
| **leave-behind.pdf** / `.html` | One-page flyer: pitch, services, the free-trial offer, contact | Hand to an owner/manager on a walk-up; attach to a follow-up email |
| **before-after.pdf** / `.html` | One-page portfolio sheet with 3 before/after slots | Proof of work — fill with real photos, then it becomes your strongest closer |

The **PDFs are ready to print today** (with placeholders). The **HTML files are the editable source** — change them, then re-render the PDF (steps below).

---

## 1. Fill in the placeholders (do this first)

Open each `.html` in any text editor and replace the bracketed bits:

- `[ROB'S LAST NAME]`
- `[YOUR PHONE]`
- `[YOUR EMAIL]`
- `[@ONYXDETAILCOLLECTIVE]` — Instagram handle or website
- The QR-code box on the leave-behind — drop in a QR image that links to a booking page, site, or IG (generate one free at any QR site), or delete the box.
- On the before/after sheet: replace each `[Vehicle / client type]` and caption line.

## 2. Add real before/after photos

1. Put image files in **`marketing/photos/`**.
2. In `before-after.html`, find each slot, e.g.:
   ```html
   <div class="slot empty"><span class="tag before">BEFORE</span>...</div>
   ```
   Replace the placeholder with a real image by setting a background and removing `empty`:
   ```html
   <div class="slot" style="background-image:url('photos/1-before.jpg')"></div>
   ```
   (Keep the `<span class="tag before">BEFORE</span>` inside if you still want the label.)
3. Re-render (next step).

> Real before/after shots are the single biggest upgrade to this kit — a muddy work truck next to a gleaming one sells the trial by itself.

## 3. Re-render the PDF after any edit

From this folder:

```bash
CHROME="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
"$CHROME" --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="leave-behind.pdf" "file://$PWD/leave-behind.html"
"$CHROME" --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="before-after.pdf" "file://$PWD/before-after.html"
```

No Chrome on the command line? Just **open the `.html` in any browser → Print → Save as PDF** (set margins to "None", paper to Letter).

## Design notes
- Letter size (8.5×11"), single page each, black + champagne-gold "Onyx" palette.
- Built to print clean in **color** (the gold + black is the brand) and still read fine in grayscale.
- Everything's plain HTML/CSS — no fonts to install, no dependencies.
