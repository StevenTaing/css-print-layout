# 📃 CSS Print Layout

A lightweight **browser-based print layout system** that simulates real paper sheet (A4, A5, Letter) directly on screen and produces clean, consistent output when printing.

**Recommended Use Cases**

✔ In-browser document preview
✔ Invoice / report printing
✔ Static page numbering
✔ Print-friendly layouts

## ✨ Features

- Multiple paper sizes and orientations
- Page counters (Page 1, Page 2, …)
- Header and footer images
- Watermarks
- Screen preview vs print mode
- Print-specific utility classes

## 🛠️ Core Concepts

Integrating this stylesheet is simple, wrap the content you want to simulate as printed pages.

```html
<div class="A4 page-number-br">
  <div class="page">...</div>
  <div class="page">...</div>
</div>
```

- The wrapper (`.A4`, `.A5`, `.letter`) defines the paper size
- Add `.landscape` - to switch orientation (default is **portrait**)
- Page number (`.page-number-tr`, `.page-number-br`, ect) control the page number position.
- Each `.page` element represents **one physical sheet of paper**.
- Each `.page` automatically increments the page counter
- Pages are stacked vertically for on‑screen preview

## 🚀 Usage

### 1. Getting started

- Download `print-layout.css` file from GitHub or oad it directly.

- Copy downloaded stylesheet to your project and load it into `<head>`

```html
<link href="styles/print-layout.css" rel="stylesheet" />
```

- or Direct link:

```html
<link
  href="[https://github.com/StevenTaing/css-print-layout/blob/master/styles/print-layout.css](https://github.com/StevenTaing/css-print-layout/blob/main/styles/print-layout.css)"
  rel="stylesheet"
/>
```

### 2. Configuration

- Overrides Global CSS Variables by placing them inside a
  `<style>` tag in `<head>` or inside your main stylesheet

```css
* {
  margin: 0;
  padding: 0;
}

:root {
  --header-image: url(../images/logo-long.png);
  --header-height: 20mm;
  --footer-image: url(../images/footer.png);
  --footer-height: 10mm;

  --page-top-padding: 30mm; /* Should be >= header height */
  --page-bottom-padding: 15mm; /* Should be >= footer height */
  --page-left-padding: 5mm;
  --page-right-padding: 5mm;

  --watermark-image: url(../images/watermarks.png);
}
```

- Inside `<body>`, add a wrapper element, can be `<main>`, `<section>`, `<div>` or any tag that suitable to your project
- Apply class `A4`, `A5`, or `letter` to set paper size
  - **A4**: 210 × 296 mm
  - **A5**: 148 × 209 mm
  - **Letter**: 216 × 279 mm
- Add class `landscape` if needed
- Add a page‑number class to enable numbering

| Class             | Position     |
| ----------------- | ------------ |
| `.page-number-tl` | Top Left     |
| `.page-number-tr` | Top Right    |
| `.page-number-bl` | Bottom Left  |
| `.page-number-br` | Bottom Right |

**Example:**

```html
<body>
  <!-- Wrapper Element -->
  <main class="A4 landscape page-number-tr">
    <!-- Paper Sheet Element (Add many as needed) -->
    <section class="page">
      <!-- Content Here-->
    </section>
  </main>
</body>
```

### 3. Print Utility Classes

Use these utilities to remove or adjust styles specifically during printing

#### Visibility

- `.print-none` → hides the element during print

#### Margin

- `.m-print-none` → remove all margin
- `.mt-print-none` → remove top margin
- `.mb-print-none` → remove bottom margin
- `.ml-print-none` → remove left margin
- `.mr-print-none` → remove right margin

#### Padding

- `.p-print-none` → remove all padding
- `.pt-print-none` → remove top padding
- `.pb-print-none` → remove bottom padding
- `.pl-print-none` → remove left padding
- `.pr-print-none` → remove right padding

#### Others

- `.b-print-none` → removes borders
- `.bg-print-none` → removes backgrounds

**Example:** A button visible on screen but hidden when printing:

```html
<button
  style="position: absolute; top: 5mm; right: 5mm; padding: 0.5rem"
  class="print-none"
  onclick="window.print()"
>
  🖨️ Print Preview
</button>
```

### 4. Limitations

- ❌ No total page count (`Page X of Y`) without JavaScript or paged engines
- ❌ Depends on browser print accuracy
- ❌ Header/footer text shares the same pseudo-element as images
- ❌ No automatic pagination when content exceeds page height

## 📸 Screenshots

![screenshot1](https://github.com/StevenTaing/nuxt-ui-image-cropper/blob/master/images/screenshot-1.png)
![screenshot2](https://github.com/StevenTaing/nuxt-ui-image-cropper/blob/master/images/screenshot-2.png)

---

## 📄 License

MIT © Heangleng (Steven), Taing

---

## 🤝 Contributing

Contributions are welcome!
If you’d like to add new features or fix bugs, feel free to fork the repo and submit a pull request.

---

## 📫 Connect with me:

[![Email](https://img.shields.io/badge/-taing.steven@gmail.com-ffffff?style=flat&logo=Gmail&logoColor=EA4335)](mailto:taing.steven@gmail.com)&nbsp;
[![Facebook](https://img.shields.io/badge/-@taing.steven-ffffff?style=flat&logo=Facebook&logoColor=1877F2)](https://www.facebook.com/taing.steven/)&nbsp;
[![Instagram](https://img.shields.io/badge/-@heanglengtaing-ffffff?style=flat&logo=Instagram&logoColor=F70C4C)](https://www.instagram.com/heanglengtaing/)
