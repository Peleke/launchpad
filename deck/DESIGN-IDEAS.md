# Design Ideas: Stunning Dark Theme Deck / One-Pager / Landing Page

Theme constants: `#0d1117` background, `#4DCFC9` teal accent, `#eee0cc` warm cream text, `#e6edf3` body text.

Slidev stack: Vue + UnoCSS. All techniques below are CSS/SVG only (no heavy JS libs).

---

## 1. Heading Treatments (10 techniques)

### 1A. Gradient Text (teal-to-cream sweep)

Replace plain `color: #eee0cc` headings with a gradient that sweeps from teal to cream.

```css
h2 {
  background: linear-gradient(135deg, #4DCFC9 0%, #eee0cc 100%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent; /* fallback for non-webkit */
}
```

**Variant -- animated gradient shimmer on slide enter:**

```css
@keyframes gradient-shift {
  0%   { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}

h2.shimmer {
  background: linear-gradient(90deg, #4DCFC9, #eee0cc, #4DCFC9);
  background-size: 200% 100%;
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient-shift 3s ease-in-out forwards;
}
```

This makes the heading appear to "light up" from teal through cream and back. Use `forwards` so it settles after one cycle instead of looping.

### 1B. Split-Color Headings (first word teal, rest cream)

Wrap the first word in a `<span>` in the Markdown. Works natively in Slidev since it renders HTML inside Markdown.

```html
## <span class="teal">Evidence</span> Wall
```

```css
h2 {
  color: #eee0cc;
}
h2 .teal {
  color: #4DCFC9;
}
```

This is dead simple and creates instant visual hierarchy. Use it for every section heading -- the first word becomes the "anchor" the eye grabs.

### 1C. Animated Underline (grows from left on slide enter)

A gradient underline that draws itself under the heading when the slide appears.

```css
h2 {
  position: relative;
  display: inline-block;
  color: #eee0cc;
}

h2::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, #4DCFC9, transparent);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.6s cubic-bezier(0.22, 1, 0.36, 1);
}

/* Trigger on slide-enter: Slidev adds .slidev-page class when active */
.slidev-page h2::after {
  transform: scaleX(1);
}
```

**Variant -- hover-only underline for interactive slides:**

```css
h2:hover::after {
  transform: scaleX(1);
}
```

### 1D. Letterpress / Emboss Effect on Dark Background

Creates a subtle 3D pressed-into-surface look. Works beautifully on #0d1117.

```css
/* Engraved (pressed-in) -- lighter shadow below text */
h2.engraved {
  color: rgba(238, 224, 204, 0.7);
  text-shadow: 0 1px 1px rgba(255, 255, 255, 0.08);
}

/* Embossed (raised) -- dark shadow below, light highlight above */
h2.emboss {
  color: rgba(238, 224, 204, 0.85);
  text-shadow:
    0 -1px 0 rgba(0, 0, 0, 0.6),
    0 1px 0 rgba(255, 255, 255, 0.08);
}
```

Use `rgba` instead of hex so the shadows blend with any background variant. The engraved style is subtle and sophisticated -- best for slide titles where you want elegance over loudness.

### 1E. Teal Neon Glow

A soft neon glow radiating from the heading text. High impact on dark backgrounds.

```css
h2.glow {
  color: #4DCFC9;
  text-shadow:
    0 0 7px rgba(77, 207, 201, 0.5),
    0 0 20px rgba(77, 207, 201, 0.3),
    0 0 40px rgba(77, 207, 201, 0.15);
}
```

**Important:** Do NOT go full neon (6+ shadow layers) -- it looks cheap. Two to three shadow layers max. The `0.5 / 0.3 / 0.15` opacity cascade keeps it tasteful.

### 1F. Text Shimmer Sweep (on slide enter)

A highlight that sweeps across the heading text once, like light reflecting off metal.

```css
@keyframes shimmer-sweep {
  0%   { background-position: -200% 0; }
  100% { background-position: 200% 0; }
}

h2.text-shimmer {
  background: linear-gradient(
    90deg,
    #eee0cc 0%,
    #eee0cc 40%,
    #4DCFC9 50%,
    #eee0cc 60%,
    #eee0cc 100%
  );
  background-size: 200% 100%;
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: shimmer-sweep 2s ease-in-out 0.3s forwards;
}
```

The 0.3s delay lets the slide finish transitioning before the shimmer fires. The teal "highlight band" at 50% creates the sweep. `forwards` stops it at the end (heading stays cream).

---

## 2. Subheading & Metadata Styling

### 2A. Monospace Pill Badge for Dates

Turn "Validation Summary -- 2026-03-06" into a styled badge.

```html
<p class="subtitle">
  Validation Summary
  <span class="date-badge">2026-03-06</span>
</p>
```

```css
.subtitle {
  color: #eee0cc;
  font-size: 1.5rem;
  font-weight: 600;
  letter-spacing: 0.02em;
}

.date-badge {
  display: inline-block;
  font-family: 'Fira Code', monospace;
  font-size: 0.85rem;
  color: #4DCFC9;
  background: rgba(77, 207, 201, 0.10);
  border: 1px solid rgba(77, 207, 201, 0.25);
  border-radius: 999px;
  padding: 2px 12px;
  margin-left: 8px;
  vertical-align: middle;
  letter-spacing: 0.04em;
}
```

### 2B. Animated Pipeline Flow with SVG Line Drawing

Replace the plain text "signal-scan -> decision-log -> persona-extract -> ..." with an SVG that draws itself.

```html
<svg class="pipeline-flow" viewBox="0 0 800 50" xmlns="http://www.w3.org/2000/svg">
  <!-- Connecting line -->
  <line class="pipeline-line" x1="0" y1="25" x2="800" y2="25"
        stroke="#4DCFC9" stroke-width="2" stroke-dasharray="800" stroke-dashoffset="800" />

  <!-- Stage labels (positioned along the line) -->
  <text x="20"  y="20" class="pipeline-label">signal-scan</text>
  <text x="160" y="20" class="pipeline-label">decision-log</text>
  <text x="310" y="20" class="pipeline-label">persona-extract</text>
  <text x="485" y="20" class="pipeline-label">offer-scope</text>
  <text x="610" y="20" class="pipeline-label">pitch</text>
  <text x="700" y="20" class="pipeline-label">assets</text>

  <!-- Arrow dots at each stage -->
  <circle cx="140"  cy="25" r="4" class="pipeline-dot" style="animation-delay: 0.3s" />
  <circle cx="290"  cy="25" r="4" class="pipeline-dot" style="animation-delay: 0.6s" />
  <circle cx="465"  cy="25" r="4" class="pipeline-dot" style="animation-delay: 0.9s" />
  <circle cx="590"  cy="25" r="4" class="pipeline-dot" style="animation-delay: 1.2s" />
  <circle cx="685"  cy="25" r="4" class="pipeline-dot" style="animation-delay: 1.5s" />
</svg>
```

```css
@keyframes draw-line {
  to { stroke-dashoffset: 0; }
}

@keyframes dot-appear {
  0%   { opacity: 0; r: 0; }
  50%  { opacity: 1; r: 6; }
  100% { opacity: 1; r: 4; }
}

.pipeline-line {
  animation: draw-line 2s ease-in-out forwards;
}

.pipeline-label {
  fill: #eee0cc;
  font-family: 'Fira Code', monospace;
  font-size: 12px;
  opacity: 0;
  animation: dot-appear 0.4s ease-out forwards;
}

/* Stagger label appearance */
.pipeline-label:nth-of-type(1) { animation-delay: 0.0s; }
.pipeline-label:nth-of-type(2) { animation-delay: 0.3s; }
.pipeline-label:nth-of-type(3) { animation-delay: 0.6s; }
.pipeline-label:nth-of-type(4) { animation-delay: 0.9s; }
.pipeline-label:nth-of-type(5) { animation-delay: 1.2s; }
.pipeline-label:nth-of-type(6) { animation-delay: 1.5s; }

.pipeline-dot {
  fill: #4DCFC9;
  opacity: 0;
  animation: dot-appear 0.3s ease-out forwards;
}
```

The line draws itself left-to-right, then each stage label and connector dot appears with staggered delays. This replaces the boring flat text with something that tells a story about the flow.

### 2C. CSS Typewriter Effect for Subheadings

A typewriter that "types out" the subtitle text. Best for the cover slide.

```css
@keyframes typing {
  from { width: 0; }
  to   { width: 100%; }
}

@keyframes blink-caret {
  50% { border-color: transparent; }
}

.typewriter {
  font-family: 'Fira Code', monospace;
  color: #4DCFC9;
  overflow: hidden;
  white-space: nowrap;
  border-right: 2px solid #4DCFC9;
  width: 0;
  animation:
    typing 2.5s steps(40) 0.5s forwards,
    blink-caret 0.75s step-end infinite;
}
```

```html
<p class="typewriter">Validation Summary &mdash; 2026-03-06</p>
```

**Caveat:** Typewriter only works with `white-space: nowrap` so it is single-line only. Make sure the text fits the slide width.

### 2D. Breadcrumb Trail Styling for Pipeline Steps

An alternative to the SVG pipeline -- pure CSS breadcrumb with chevrons.

```html
<div class="breadcrumb-pipeline">
  <span class="step active">signal-scan</span>
  <span class="step">decision-log</span>
  <span class="step">persona-extract</span>
  <span class="step">offer-scope</span>
  <span class="step">pitch</span>
  <span class="step">assets</span>
</div>
```

```css
.breadcrumb-pipeline {
  display: flex;
  align-items: center;
  gap: 0;
  font-family: 'Fira Code', monospace;
  font-size: 0.8rem;
}

.breadcrumb-pipeline .step {
  color: #8b949e;
  padding: 4px 14px 4px 24px;
  position: relative;
  background: rgba(77, 207, 201, 0.04);
  transition: all 0.3s ease;
}

.breadcrumb-pipeline .step:first-child {
  padding-left: 14px;
  border-radius: 4px 0 0 4px;
}

.breadcrumb-pipeline .step:last-child {
  border-radius: 0 4px 4px 0;
}

/* Chevron separator via pseudo-element */
.breadcrumb-pipeline .step + .step::before {
  content: '';
  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  border-left: 8px solid rgba(77, 207, 201, 0.15);
  border-top: 14px solid transparent;
  border-bottom: 14px solid transparent;
}

.breadcrumb-pipeline .step.active {
  color: #4DCFC9;
  background: rgba(77, 207, 201, 0.12);
}
```

---

## 3. Cover Slide Improvements

### 3A. Animated Dot Grid Background (CSS only)

A subtle grid of dots that fades in and slowly pulses. No JS.

```css
.cover-bg {
  position: relative;
  overflow: hidden;
}

.cover-bg::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: radial-gradient(
    circle at center,
    rgba(77, 207, 201, 0.12) 1px,
    transparent 1px
  );
  background-size: 32px 32px;
  animation: grid-fade 4s ease-in-out infinite alternate;
}

@keyframes grid-fade {
  0%   { opacity: 0.3; }
  100% { opacity: 0.7; }
}
```

The dots are teal at 12% opacity so they read as texture, not distraction. The slow pulse adds life without competing with text.

### 3B. Vignette + Radial Gradient Halo

A soft radial glow behind the title text area, like a spotlight.

```css
.cover-bg::after {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(
    ellipse 60% 50% at 50% 45%,
    rgba(77, 207, 201, 0.06) 0%,
    transparent 70%
  );
  pointer-events: none;
}
```

This creates a barely-visible teal halo centered behind the heading. Combine with the dot grid for depth.

### 3C. Glassmorphism Title Card

A frosted-glass card floating over the dot grid background.

```css
.glass-card {
  background: rgba(13, 17, 23, 0.6);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1px solid rgba(77, 207, 201, 0.15);
  border-radius: 16px;
  padding: 40px 56px;
  box-shadow:
    0 8px 32px rgba(0, 0, 0, 0.3),
    inset 0 1px 0 rgba(238, 224, 204, 0.05);
}
```

The `inset` box-shadow creates a subtle top-edge highlight that sells the glass effect. The border uses teal at 15% opacity -- visible but not harsh.

**Usage in Slidev cover slide:**

```html
---
layout: cover
background: '#0d1117'
class: cover-bg
---

<div class="glass-card mx-auto max-w-2xl text-center">
  <h1 class="text-4xl font-extrabold shimmer">Ambient Content Engine</h1>
  <p class="typewriter mt-4">Validation Summary &mdash; 2026-03-06</p>
</div>
```

### 3D. Animated Grid Lines (CSS only)

Faint grid lines that slowly scroll, giving a sense of motion without particles.

```css
@keyframes grid-scroll {
  0%   { background-position: 0 0; }
  100% { background-position: 0 32px; }
}

.animated-grid::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(77, 207, 201, 0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(77, 207, 201, 0.04) 1px, transparent 1px);
  background-size: 32px 32px;
  animation: grid-scroll 8s linear infinite;
  mask-image: radial-gradient(ellipse 70% 70% at 50% 50%, black 30%, transparent 80%);
  -webkit-mask-image: radial-gradient(ellipse 70% 70% at 50% 50%, black 30%, transparent 80%);
}
```

The `mask-image` makes the grid fade out toward the edges so it does not look like a tiled floor. The scroll is slow (8s) and linear -- barely perceptible, which is the point.

### 3E. Gradient Border Glow Card (animated on slide enter)

A card with an animated conic gradient border that rotates once and settles.

```css
@property --angle {
  syntax: '<angle>';
  initial-value: 0deg;
  inherits: false;
}

@keyframes border-rotate {
  to { --angle: 360deg; }
}

.glow-border-card {
  position: relative;
  padding: 40px 56px;
  border-radius: 16px;
  background: #0d1117;
  isolation: isolate;
}

.glow-border-card::before {
  content: '';
  position: absolute;
  inset: -2px;
  border-radius: inherit;
  background: conic-gradient(
    from var(--angle),
    transparent 0%,
    #4DCFC9 25%,
    transparent 50%,
    #eee0cc 75%,
    transparent 100%
  );
  z-index: -1;
  animation: border-rotate 3s ease-in-out forwards;
}

.glow-border-card::after {
  content: '';
  position: absolute;
  inset: 2px;
  border-radius: inherit;
  background: #0d1117;
  z-index: -1;
}
```

**Note:** `@property` is supported in Chromium and Safari 16.4+. It will NOT animate in Firefox (falls back to static gradient). This is fine for exported PDFs and live presentations, but check your target.

---

## 4. Slide Transitions & Micro-Interactions

### 4A. Staggered v-click Reveals (built into Slidev)

Add `animation-delay` to sequential v-click elements. The current `style.css` already does fade+translateY. Enhance with stagger:

```css
/* Stagger sequential v-click reveals */
.slidev-vclick-target:nth-child(1) { transition-delay: 0.0s; }
.slidev-vclick-target:nth-child(2) { transition-delay: 0.1s; }
.slidev-vclick-target:nth-child(3) { transition-delay: 0.15s; }
.slidev-vclick-target:nth-child(4) { transition-delay: 0.2s; }
```

### 4B. v-motion Directive (built into Slidev via @vueuse/motion)

Slidev bundles @vueuse/motion. Use it for more expressive animations than v-click:

```html
<div
  v-motion
  :initial="{ opacity: 0, y: 40, scale: 0.95 }"
  :enter="{ opacity: 1, y: 0, scale: 1, transition: { duration: 600, delay: 200 } }"
>
  <h2>Evidence Wall</h2>
</div>
```

This gives you per-element control with Spring physics and delays without writing CSS.

### 4C. Custom Slide Transition (teal wipe)

Create a custom transition that wipes the slide with a teal flash.

In `slides.md` frontmatter:

```yaml
transition: teal-wipe
```

In `style.css`:

```css
.teal-wipe-enter-active,
.teal-wipe-leave-active {
  transition: all 0.6s cubic-bezier(0.22, 1, 0.36, 1);
}

.teal-wipe-enter-from {
  opacity: 0;
  clip-path: inset(0 100% 0 0);
}

.teal-wipe-enter-to {
  opacity: 1;
  clip-path: inset(0 0 0 0);
}

.teal-wipe-leave-from {
  opacity: 1;
  clip-path: inset(0 0 0 0);
}

.teal-wipe-leave-to {
  opacity: 0;
  clip-path: inset(0 0 0 100%);
}
```

`clip-path: inset()` creates a rectangular reveal/hide. The slide appears to wipe from left to right. Pair with a full-width teal border on the leading edge for extra punch.

### 4D. Scale + Blur Entry for Images/SVGs

Images currently fade+scale(0.96). Enhance with a blur that sharpens:

```css
.slidev-vclick-hidden img,
.slidev-vclick-hidden object {
  opacity: 0 !important;
  transform: scale(0.94);
  filter: blur(8px);
}

.slidev-vclick-current img,
.slidev-vclick-prior img,
.slidev-vclick-current object,
.slidev-vclick-prior object {
  opacity: 1;
  transform: scale(1);
  filter: blur(0);
  transition: all 0.5s cubic-bezier(0.22, 1, 0.36, 1) !important;
}
```

The blur-to-sharp transition makes images feel like they're coming into focus. Very cinematic.

### 4E. Blockquote Slide-In from Left

For the Reddit quotes slide, make each quote slide in from the left edge:

```css
.slidev-vclick-hidden blockquote {
  opacity: 0 !important;
  transform: translateX(-30px);
}

.slidev-vclick-current blockquote,
.slidev-vclick-prior blockquote {
  opacity: 1;
  transform: translateX(0);
  transition: all 0.5s cubic-bezier(0.22, 1, 0.36, 1) !important;
}
```

---

## 5. Layout Patterns for Data-Heavy Slides

### 5A. Metric Card Grid (replaces tables for SDP Scoring, Revenue Model)

Instead of a table, use a CSS grid of cards -- each card shows one metric.

```html
<div class="metric-grid">
  <div class="metric-card">
    <span class="metric-value teal">54<span class="metric-unit">/60</span></span>
    <span class="metric-label">SDP Score</span>
  </div>
  <div class="metric-card">
    <span class="metric-value teal">$3-5K</span>
    <span class="metric-label">Setup Fee</span>
  </div>
  <div class="metric-card">
    <span class="metric-value teal">$1K</span>
    <span class="metric-label">/mo Retainer</span>
  </div>
  <div class="metric-card">
    <span class="metric-value coral">8 wk</span>
    <span class="metric-label">Kill Decision</span>
  </div>
</div>
```

```css
.metric-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  gap: 16px;
  max-width: 720px;
  margin: 24px auto;
}

.metric-card {
  background: rgba(77, 207, 201, 0.04);
  border: 1px solid rgba(77, 207, 201, 0.12);
  border-radius: 12px;
  padding: 20px 16px;
  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 8px;
  transition: border-color 0.3s ease, background 0.3s ease;
}

.metric-card:hover {
  border-color: rgba(77, 207, 201, 0.3);
  background: rgba(77, 207, 201, 0.08);
}

.metric-value {
  font-size: 2rem;
  font-weight: 800;
  line-height: 1;
}

.metric-unit {
  font-size: 1rem;
  font-weight: 400;
  opacity: 0.6;
}

.metric-label {
  font-size: 0.85rem;
  color: #8b949e;
  text-transform: uppercase;
  letter-spacing: 0.06em;
}
```

### 5B. Vertical Timeline Layout (replaces Execution Calendar table)

A timeline with a vertical line and milestone nodes.

```html
<div class="timeline">
  <div class="timeline-item">
    <span class="timeline-marker"></span>
    <div class="timeline-content">
      <span class="timeline-date">Wk 1-3</span>
      <span class="timeline-title">LinkedIn warm-up</span>
      <span class="timeline-desc">3-5 posts/wk baseline</span>
    </div>
  </div>
  <div class="timeline-item">
    <span class="timeline-marker active"></span>
    <div class="timeline-content">
      <span class="timeline-date">Wk 4</span>
      <span class="timeline-title">Article 1 drops</span>
      <span class="timeline-desc">LinkedIn + Reddit cross-post</span>
    </div>
  </div>
  <!-- ... more items -->
</div>
```

```css
.timeline {
  position: relative;
  padding-left: 32px;
  max-width: 600px;
  margin: 16px auto;
}

/* Vertical line */
.timeline::before {
  content: '';
  position: absolute;
  left: 11px;
  top: 4px;
  bottom: 4px;
  width: 2px;
  background: linear-gradient(to bottom, #4DCFC9, rgba(77, 207, 201, 0.15));
}

.timeline-item {
  position: relative;
  padding-bottom: 24px;
  display: flex;
  align-items: flex-start;
  gap: 16px;
}

.timeline-marker {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: #0d1117;
  border: 2px solid rgba(77, 207, 201, 0.4);
  flex-shrink: 0;
  margin-top: 4px;
  position: absolute;
  left: -26px;
}

.timeline-marker.active {
  background: #4DCFC9;
  border-color: #4DCFC9;
  box-shadow: 0 0 8px rgba(77, 207, 201, 0.4);
}

.timeline-date {
  font-family: 'Fira Code', monospace;
  font-size: 0.75rem;
  color: #4DCFC9;
  min-width: 48px;
}

.timeline-title {
  color: #eee0cc;
  font-weight: 600;
  font-size: 1rem;
}

.timeline-desc {
  color: #8b949e;
  font-size: 0.85rem;
}

.timeline-content {
  display: flex;
  flex-direction: column;
  gap: 2px;
}
```

### 5C. Two-Column Split Layout (text left, visual right)

For slides with one key insight plus one visual. Uses CSS grid.

```css
.split-layout {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 48px;
  align-items: center;
  height: 100%;
  padding: 0 32px;
}

.split-layout .text-side {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.split-layout .visual-side {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

Use Slidev's `layout: two-cols` built-in, or create a custom layout at `layouts/split.vue`:

```vue
<template>
  <div class="slidev-layout split-layout">
    <div class="text-side">
      <slot name="default" />
    </div>
    <div class="visual-side">
      <slot name="right" />
    </div>
  </div>
</template>
```

### 5D. Horizontal Comparison Cards (replaces competitive map table)

Side-by-side cards with a "vs" divider for comparison slides.

```css
.comparison-row {
  display: flex;
  gap: 16px;
  align-items: stretch;
  max-width: 740px;
  margin: 24px auto;
}

.comparison-card {
  flex: 1;
  background: rgba(77, 207, 201, 0.03);
  border: 1px solid rgba(77, 207, 201, 0.1);
  border-radius: 12px;
  padding: 20px;
  position: relative;
}

.comparison-card.highlight {
  border-color: #4DCFC9;
  box-shadow: 0 0 20px rgba(77, 207, 201, 0.08);
}

.comparison-card .card-name {
  font-size: 1.1rem;
  color: #eee0cc;
  font-weight: 700;
  margin-bottom: 8px;
}

.comparison-card .card-price {
  font-family: 'Fira Code', monospace;
  font-size: 1.3rem;
  color: #4DCFC9;
  font-weight: 700;
}

.comparison-card .card-detail {
  color: #8b949e;
  font-size: 0.85rem;
  margin-top: 4px;
}

.vs-divider {
  display: flex;
  align-items: center;
  color: #8b949e;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.1em;
}
```

### 5E. Stat Bar (horizontal progress bar for scores)

Replace the SDP scoring table with visual progress bars.

```css
.stat-bar-container {
  max-width: 600px;
  margin: 8px auto;
}

.stat-bar-row {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 12px;
}

.stat-bar-label {
  flex: 0 0 180px;
  text-align: right;
  color: #eee0cc;
  font-size: 0.9rem;
  font-weight: 500;
}

.stat-bar-track {
  flex: 1;
  height: 8px;
  background: rgba(77, 207, 201, 0.08);
  border-radius: 4px;
  overflow: hidden;
}

.stat-bar-fill {
  height: 100%;
  background: linear-gradient(90deg, #4DCFC9, rgba(77, 207, 201, 0.6));
  border-radius: 4px;
  transition: width 0.8s cubic-bezier(0.22, 1, 0.36, 1);
}

.stat-bar-value {
  flex: 0 0 40px;
  font-family: 'Fira Code', monospace;
  font-size: 0.85rem;
  color: #4DCFC9;
  font-weight: 600;
}
```

Usage: set `width: 90%` (for 54/60) on `.stat-bar-fill` inline or via a CSS variable.

---

## 6. UnoCSS Configuration for Custom Animations

Add to `uno.config.ts` (or create it) for reusable utility classes:

```ts
import { defineConfig } from 'unocss'

export default defineConfig({
  theme: {
    animation: {
      keyframes: {
        'shimmer-sweep': `{
          0%   { background-position: -200% 0; }
          100% { background-position: 200% 0; }
        }`,
        'grid-fade': `{
          0%   { opacity: 0.3; }
          100% { opacity: 0.7; }
        }`,
        'draw-in': `{
          from { stroke-dashoffset: var(--dash-length); }
          to   { stroke-dashoffset: 0; }
        }`,
      },
      durations: {
        'shimmer-sweep': '2s',
        'grid-fade': '4s',
        'draw-in': '2s',
      },
      timingFns: {
        'shimmer-sweep': 'ease-in-out',
        'grid-fade': 'ease-in-out',
        'draw-in': 'ease-in-out',
      },
      counts: {
        'grid-fade': 'infinite',
      },
    },
  },
  shortcuts: {
    'text-gradient': 'bg-gradient-to-r from-[#4DCFC9] to-[#eee0cc] bg-clip-text text-transparent',
    'glass': 'bg-[rgba(13,17,23,0.6)] backdrop-blur-16 border border-[rgba(77,207,201,0.15)] rounded-2xl',
    'badge-teal': 'font-mono text-sm text-[#4DCFC9] bg-[rgba(77,207,201,0.1)] border border-[rgba(77,207,201,0.25)] rounded-full px-3 py-0.5',
  },
})
```

---

## 7. Quick Wins -- Recommended Combinations

### Cover Slide (Slide 1)

Combine: dot grid background (3A) + radial halo (3B) + glass card (3C) + gradient heading (1A) + typewriter subtitle (2C).

### Section Headings (all content slides)

Combine: split-color heading (1B) + animated underline (1C). The first word in teal grabs the eye, the underline draws itself to anchor the section visually.

### Data Slides (SDP Scoring, Revenue, Kill Criteria)

Replace tables with: metric card grid (5A) or stat bars (5E). Use v-motion (4B) for staggered card reveals.

### Quote Slides (Reddit Voices)

Keep current blockquote styling. Add: slide-in from left (4E) + blur-to-sharp (4D applied to blockquote elements).

### Timeline Slides (Execution Calendar, Next Steps)

Replace table with: vertical timeline (5B). Each milestone appears via v-click with stagger (4A).

### Closing Slide

Combine: glass card (3C) + neon glow heading (1E) + animated grid (3D).

---

## Sources

### Heading & Typography
- [CSS Gradient Text](https://css-tricks.com/snippets/css/gradient-text/)
- [Animated Gradient Text](https://web.dev/articles/speedy-css-tip-animated-gradient-text)
- [30 Seconds of Code -- Engraved & Embossed Text](https://www.30secondsofcode.org/css/s/engraved-embossed-text/)
- [Neon Text with CSS](https://css-tricks.com/how-to-create-neon-text-with-css/)
- [Letterpress Effect with CSS](https://line25.com/tutorials/create-a-letterpress-effect-with-css-text-shadow/)
- [Animated Background Gradient Text](https://theadminbar.com/how-to-create-animated-background-gradient-text-with-css/)

### Underlines & Animations
- [Animating Underlines](https://css-irl.info/animating-underlines/)
- [CSS Hover Underline Animation](https://www.30secondsofcode.org/css/s/hover-underline-animation/)
- [Gradient Underline Links](https://www.amberddesign.com/gradient-underline-links-with-animation/)
- [Animated Gradient Underline Gist](https://gist.github.com/CodeMyUI/2e47212f1ebf8c7defc0b00b65ad428a)

### SVG Line Drawing
- [SVG Line Animation Works](https://css-tricks.com/svg-line-animation-works/)
- [Animated SVG Pipes Effect](https://www.webfx.com/blog/web-design/animated-svg-pipes/)
- [SVG Animation Tutorial](https://blog.logrocket.com/how-to-animate-svg-css-tutorial-examples/)

### Typewriter
- [CSS Typewriter Effect](https://css-tricks.com/snippets/css/typewriter-effect/)
- [Scalable CSS-only Typewriter](https://dev.to/afif/a-scalable-css-only-typewriter-effect-2opn)

### Cover Slide Backgrounds
- [CSS Particle Backgrounds](https://csscrafter.com/css-particle-effects/)
- [CSS Animated Background Examples](https://www.sliderrevolution.com/resources/css-animated-background/)
- [Pure CSS Particle Animation](https://github.com/Ishan2608/Pure-CSS-Particle-Animation)
- [CSS Dotted Background](https://dev.to/codingdudecom/css-dotted-background-4m20)
- [Grid and Dot Backgrounds with Tailwind](https://ibelick.com/blog/create-grid-and-dot-backgrounds-with-css-tailwind-css)

### Glassmorphism
- [Glassmorphism CSS Generator](https://ui.glass/generator)
- [Glassmorphism with Tailwind CSS](https://www.epicweb.dev/tips/creating-glassmorphism-effects-with-tailwind-css)
- [Implement Glassmorphism CSS](https://blog.logrocket.com/implement-glassmorphism-css/)

### Gradient Borders
- [Animated CSS Gradient Borders (no JS)](https://codetv.dev/blog/animated-css-gradient-border)
- [Glowing Border Animation](https://css-tip.com/glowing-border/)
- [Animated Gradient Borders Tailwind](https://cruip.com/animated-gradient-borders-with-tailwind-css/)

### Slidev Animations
- [Slidev Animation Guide](https://sli.dev/guide/animations)
- [Slidev Animation & Transitions DeepWiki](https://deepwiki.com/slidevjs/slidev/4.2-animation-and-transitions)
- [Slidev Customizations](https://sli.dev/custom/)
- [Slidev Components](https://sli.dev/builtin/components)

### Dashboard Layouts
- [CSS Grid Dashboard Cards Gist](https://gist.github.com/trooperandz/39020a1abc9e94bd874e58d753db75f4)
- [Dashboard Design Trends 2025](https://uitop.design/blog/design/top-dashboard-design-trends/)
- [CSS Dashboards Collection](https://freefrontend.com/css-dashboards/)

### UnoCSS Animations
- [UnoCSS Theme Animations Tutorial](https://tutorial.unocss.dev/1-basics/4-theme/4-theme-animations/)
- [Configure UnoCSS in Slidev](https://sli.dev/custom/config-unocss)
