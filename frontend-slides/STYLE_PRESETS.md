# Style Presets Reference

Curated visual styles for Frontend Slides. Each preset includes specific font choices, color palettes, and animation approaches to ensure distinctive, non-generic designs.

---

## Dark Themes

### 1. Neon Cyber

**Vibe:** Futuristic, techy, confident, cutting-edge

**Typography:**
- Display: `Clash Display` (700) — Bold, geometric, modern
- Body: `Satoshi` (400/500) — Clean, technical, readable

**Colors:**
```css
:root {
    --bg-primary: #0a0f1c;
    --bg-secondary: #111827;
    --text-primary: #ffffff;
    --text-secondary: #94a3b8;
    --accent: #00ffcc;
    --accent-secondary: #ff00aa;
    --glow: rgba(0, 255, 204, 0.4);
}
```

**Signature Elements:**
- Particle system background (canvas)
- Neon glow on accent elements
- Custom cursor with trail
- Grid pattern overlay
- Glitch text effect on titles

**Animation Style:**
- Medium speed (0.5-0.8s)
- Slide up + fade entrances
- Staggered reveals

---

### 2. Midnight Executive

**Vibe:** Premium, trustworthy, sophisticated, corporate

**Typography:**
- Display: `Libre Baskerville` (700) — Classic, authoritative
- Body: `Source Sans 3` (400/600) — Professional, highly readable

**Colors:**
```css
:root {
    --bg-primary: #0f172a;
    --bg-secondary: #1e293b;
    --text-primary: #f8fafc;
    --text-secondary: #94a3b8;
    --accent: #3b82f6;
    --accent-secondary: #818cf8;
    --gold: #fbbf24;
}
```

**Signature Elements:**
- Subtle gradient backgrounds
- Thin gold accent lines
- Data visualizations
- Minimal decorative elements
- Focus on whitespace

**Animation Style:**
- Fast, subtle (0.3-0.5s)
- Fade only, minimal movement
- Professional restraint

---

### 3. Deep Space

**Vibe:** Inspiring, vast, contemplative, visionary

**Typography:**
- Display: `Space Grotesk` (700) — Geometric, space-age
- Body: `DM Sans` (400/500) — Modern, friendly

**Colors:**
```css
:root {
    --bg-primary: #030712;
    --bg-secondary: #111827;
    --text-primary: #f9fafb;
    --text-secondary: #6b7280;
    --accent: #818cf8;
    --accent-secondary: #c084fc;
    --stars: rgba(255, 255, 255, 0.1);
}
```

**Signature Elements:**
- Starfield background (CSS or canvas)
- Radial gradient "spotlight" effects
- Floating elements
- Large, impactful typography
- Generous vertical spacing

**Animation Style:**
- Slow, cinematic (0.8-1.2s)
- Scale + fade entrances
- Parallax scrolling

---

### 4. Terminal Green

**Vibe:** Developer-focused, hacker aesthetic, retro-tech

**Typography:**
- Display: `JetBrains Mono` (700) — Monospace, code-like
- Body: `JetBrains Mono` (400) — Consistent monospace

**Colors:**
```css
:root {
    --bg-primary: #0d1117;
    --bg-secondary: #161b22;
    --text-primary: #c9d1d9;
    --text-secondary: #8b949e;
    --accent: #39d353;
    --accent-dim: rgba(57, 211, 83, 0.2);
    --border: #30363d;
}
```

**Signature Elements:**
- Scan line overlay effect
- Blinking cursor
- Code blocks and syntax highlighting
- ASCII art decorations
- Terminal-style borders

**Animation Style:**
- Typewriter text reveals
- Quick, snappy transitions (0.2-0.3s)
- Character-by-character reveals

---

## Light Themes

### 5. Paper & Ink

**Vibe:** Editorial, literary, thoughtful, refined

**Typography:**
- Display: `Cormorant Garamond` (700) — Elegant, editorial
- Body: `Source Serif 4` (400) — Classic, readable

**Colors:**
```css
:root {
    --bg-primary: #faf9f7;
    --bg-secondary: #f5f3ef;
    --text-primary: #1a1a1a;
    --text-secondary: #666666;
    --accent: #c41e3a;
    --border: #e5e2db;
}
```

**Signature Elements:**
- Drop caps on opening paragraphs
- Pull quotes
- Subtle paper texture
- Elegant horizontal rules
- Classic column layouts

**Animation Style:**
- Gentle fades (0.4-0.6s)
- No dramatic movements
- Refined, understated

---

### 6. Swiss Modern

**Vibe:** Clean, precise, Bauhaus-inspired, geometric

**Typography:**
- Display: `Archivo` (800) — Strong, geometric
- Body: `Nunito` (400/600) — Friendly, rounded

**Colors:**
```css
:root {
    --bg-primary: #ffffff;
    --bg-secondary: #f7f7f7;
    --text-primary: #000000;
    --text-secondary: #555555;
    --accent: #ff3300;
    --grid: rgba(0, 0, 0, 0.05);
}
```

**Signature Elements:**
- Visible grid system
- Asymmetric layouts
- Red accent sparingly
- Bold black typography
- Geometric shapes

**Animation Style:**
- Precise, mechanical (0.3-0.4s)
- Linear or ease-out easing
- Grid-aligned movements

---

## Font Pairing Quick Reference

| Vibe | Display Font | Body Font | Source |
|------|--------------|-----------|--------|
| Techy/Modern | Clash Display | Satoshi | Fontshare |
| Professional | Libre Baskerville | Source Sans 3 | Google |
| Space/Future | Space Grotesk | DM Sans | Google |
| Developer | JetBrains Mono | JetBrains Mono | JetBrains |
| Editorial | Cormorant Garamond | Source Serif 4 | Google |
| Swiss/Minimal | Archivo | Nunito | Google |
| Playful | Nunito | Nunito | Google |
| Magazine | Playfair Display | Work Sans | Google |
| Brutalist | Anton | IBM Plex Mono | Google |
| SaaS Modern | Cabinet Grotesk | Inter | Fontshare/Google |

---

## Animation Easing Reference

```css
:root {
    /* Standard curves */
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --ease-out-quart: cubic-bezier(0.25, 1, 0.5, 1);
    --ease-out-cubic: cubic-bezier(0.33, 1, 0.68, 1);

    /* Bouncy */
    --ease-bounce: cubic-bezier(0.34, 1.56, 0.64, 1);
    --ease-spring: cubic-bezier(0.175, 0.885, 0.32, 1.275);

    /* Smooth */
    --ease-smooth: cubic-bezier(0.4, 0, 0.2, 1);

    /* Snappy */
    --ease-snappy: cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
```
