# BlindMotion

**BlindMotion** (or `Blind.css`) is a zero-dependency, lightweight CSS animation library built on top of native CSS custom properties (variables). Designed for high performance and low overhead, it provides declarative utility classes for common entrance, exit, and emphasis animations while leaving complete control over timing, distances, scale, and easing in your hands.

---

## Features

* **CSS Variable First:** Every animation parameter (duration, distance, easing curve, scale factor) is exposed via `:root` and element-scoped CSS custom properties.
* **Hardware-Accelerated:** Exclusively utilizes composited properties (`transform` and `opacity`) to target 60fps execution.
* **Zero Dependencies:** Pure CSS. No JavaScript engine, build steps, or runtime overhead required.
* **Drop-in CDN Support:** Load directly from jsDelivr into any static or framework-based web project.

---

## Installation

### CDN

Include the production file directly in the `<head>` of your HTML document:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/imnotblindforreal/BlindMotion@main/Blind.css">

```

---

## Usage

Apply the base `blind-animated` class alongside your target animation class to any HTML element.

```html
<div class="blind-animated blind-fadeInUp">
  Content to animate
</div>

```

---

## Configuration & Customization

All default parameters are defined in the `:root` pseudo-class. You can override defaults globally, per-component, or via inline styles.

### Global Overrides

To modify default behavior globally across all animations, override the root variables in your custom stylesheet:

```css
:root {
  --blind-default-duration: 0.5s;
  --blind-default-ease: cubic-bezier(0.16, 1, 0.3, 1);
}

```

### Element-Specific Customization

Modify individual animation properties directly on specific elements or scoped CSS selectors:

```css
/* Customizing standard entrance distances and timing */
.hero-title {
  --blind-fadeInUp-duration: 1.2s;
  --blind-fadeInUp-distance: 60px;
}

```

```html
<!-- Inline overrides -->
<div 
  class="blind-animated blind-zoomIn" 
  style="--blind-zoomIn-duration: 0.4s; --blind-zoomIn-start-scale: 0.5;"
>
  Fast Zoom Panel
</div>

```

---

## Available Animations

| Category | Classes | Key Variables |
| --- | --- | --- |
| **Fade** | `blind-fadeIn`, `blind-fadeOut`, `blind-fadeInUp`, `blind-fadeInDown`, `blind-fadeInLeft`, `blind-fadeInRight` | `--blind-(fadeName)-duration`, `--blind-(fadeName)-ease`, `--blind-(fadeName)-distance` |
| **Slide** | `blind-slideInUp`, `blind-slideInDown`, `blind-slideInLeft`, `blind-slideInRight` | `--blind-(slideName)-duration`, `--blind-(slideName)-ease`, `--blind-(slideName)-distance` |
| **Zoom** | `blind-zoomIn`, `blind-zoomInDown`, `blind-zoomInUp`, `blind-zoomOut`, `blind-zoomOutUp` | `--blind-(zoomName)-duration`, `--blind-(zoomName)-ease`, `--blind-zoomIn-start-scale`, `--blind-zoomOut-end-scale`, `--blind-(zoomName)-distance` |
| **Bounce** | `blind-bounceIn`, `blind-bounceInUp`, `blind-bounceInDown`, `blind-bounceInLeft`, `blind-bounceInRight` | `--blind-(bounceName)-duration`, `--blind-(bounceName)-ease`, `--blind-(bounceName)-distance` |
| **Rotate** | `blind-rotateIn`, `blind-rotateInDownLeft`, `blind-rotateInDownRight`, `blind-rotateInUpLeft` | `--blind-(rotateName)-duration`, `--blind-(rotateName)-ease`, `--blind-(rotateName)-angle` |
| **Back** | `blind-backInDown`, `blind-backInUp`, `blind-backInLeft`, `blind-backInRight` | `--blind-(backName)-duration`, `--blind-(backName)-ease`, `--blind-(backName)-distance`, `--blind-(backName)-scale` |
---

## Browser Support

Supported in all modern, evergreen browsers supporting CSS Custom Properties (`var()`) and CSS Animations:

* Chrome 49+
* Firefox 31+
* Safari 9.1+
* Edge 15+

---

## License

Distributed under the MIT License. See `LICENSE` for more information.
