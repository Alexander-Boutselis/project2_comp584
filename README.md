# project2_comp584

https://alexander-boutselis.github.io/project2_comp584/

# COMP 584 – Week 6 Flexbox Layout

This project is a responsive multi-row layout built with **HTML** and **CSS Flexbox**.

It demonstrates:
- A 4-column flex grid on desktop
- Different layouts for tablet and mobile using **media queries**
- Reordering items using the `order` property
- A custom row using additional Flexbox properties

Open `index.html` in a browser to view the page.

---

## Files

- `index.html` – page structure and content
- `style.css` – all layout and styling rules
- `assets/desktop.png` – target desktop layout reference  
- `assets/tablet.png` – target tablet layout reference  
- `assets/mobile.png` – target mobile layout reference  

*(asset paths may differ depending on how your instructor set up the starter code)*

---

## How to Run

1. Place `index.html`, `style.css`, and the `assets` folder in the same project directory.
2. Open `index.html` in a web browser.
3. Resize the browser window to see the layout change for:
   - **Desktop** (≥ 768px)
   - **Tablet** (≈ 480px–767px)
   - **Mobile** (< 480px)

---

## Assignment Instructions (What this project implements)

You are given starter HTML/CSS and asset screenshots. The goal is to finish the layout so that the page matches the provided screenshots at desktop, tablet, and mobile sizes.

You may change the **theme/content/images** (e.g., not dogs), but the **layout behavior** must remain the same.

### General Requirements

- Use **Flexbox** for layout.
- Use **media queries** to change the layout at different breakpoints.
- Implement a 4-column grid system using classes like `.col-1`, `.col-2`, `.col-3`, `.col-4`.
- Each “row” is a flex container (`.row`) whose children are flex items.
- The layout for each row must match the example screenshots for:
  - Desktop (`desktop.png`)
  - Tablet (`tablet.png`)
  - Mobile (`mobile.png`)

---

## Row-by-Row Requirements

### Row 1 – Four Individual Boxes

- **Desktop:** four equal-width columns (4 cards in a row).
- **Tablet:** two cards per row.
- **Mobile:** one card per row (stacked).
- Implemented using four `<article class="col-1">` inside `.row.row-1`.

### Row 2 – Content + Image (Two Columns)

- **Desktop:** two equal-width columns (text on one side, image on the other).
- **Tablet:** two columns or stacked layout as shown in `tablet.png`.
- **Mobile:** stacked single-column layout.
- Implemented using two `<article class="col-2">` inside `.row.row-2`.

### Row 3 – 1–3 Layout

- **Desktop:**
  - Left item: **1 column wide** (`.col-1`)
  - Right item: **3 columns wide** (`.col-3`)
- **Tablet:** layout must match `tablet.png` (usually two equal columns).
- **Mobile:** stacked single-column layout.
- Implemented in `.row.row-3` with one `.col-1` and one `.col-3`.

### Row 4 – Full-Width Row

- **Desktop:** a **single item spanning all 4 columns** (`.col-4`).
- **Tablet:** follows `tablet.png` (often still full-width).
- **Mobile:** full-width stacked.
- Implemented in `.row.row-4` with one `.col-4`.

### Row 5 – 1–2–1 Layout + Reordering

- **Desktop:**
  - Left item: 1 column wide (`.col-1.item-a`)
  - Center item: 2 columns wide (`.col-2.item-b`)
  - Right item: 1 column wide (`.col-1.item-c`)
- **Tablet and Mobile:**
  - Layout and visual **order** must match the screenshots.
  - The HTML order stays the same; **visual order changes using the Flexbox `order` property**.
- This row demonstrates:
  - Column widths using `flex-basis`/`flex` on `.col-1` / `.col-2`
  - Item reordering with `order` in media queries.

> **Key property for this row:** `order`

```css
/* Example: change order at different breakpoints */
.row-5 .item-a { order: 1; }
.row-5 .item-b { order: 2; }
.row-5 .item-c { order: 3; }

/* Tablet override example */
@media (min-width: 480px) and (max-width: 767px) {
  .row-5 .item-a { order: 2; }
  .row-5 .item-b { order: 1; }
  .row-5 .item-c { order: 3; }
}
