# gx-zhks platform mapping

## HTML/CSS

Load fonts with system fallbacks:

```css
body {
  font-family: Inter, "PingFang SC", "Microsoft YaHei", "Helvetica Neue", Arial, sans-serif;
}
```

Optional Tabler Icons:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@3.41.1/dist/tabler-icons.min.css">
```

If the CDN cannot load, use a local line-icon fallback instead of mixing icon libraries:

```css
.ti {
  width: 1.1em;
  height: 1.1em;
  display: inline-grid;
  place-items: center;
  line-height: 1;
  flex: none;
}

.ti::before {
  content: "";
  width: .86em;
  height: .86em;
  display: block;
  border: 1.8px solid currentColor;
  border-radius: .24em;
}

.ti-chevron-right::before,
.ti-send::before {
  width: .52em;
  height: .52em;
  border-left: 0;
  border-bottom: 0;
  border-radius: 0;
  transform: rotate(45deg);
}
```

Set CSS variables first:

```css
:root {
  --gx-sidebar: #0b1320;
  --gx-page: #eef3f8;
  --gx-card: rgba(255,255,255,.95);
  --gx-navy: #020617;
  --gx-blue: #1d62cf;
  --gx-cyan: #22d3ee;
  --gx-muted: #64748b;
  --gx-border: #e2e8f0;
  --gx-radius-card: 12px;
  --gx-radius-hero: 28px;
  --gx-shadow-card: 0 18px 40px rgba(15, 23, 42, .08);
}
```

Use a two-zone app layout:

```css
.app {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 256px minmax(0, 1fr);
  background: var(--gx-page);
}
```

## React/Tailwind

Map tokens to Tailwind classes without inventing a new palette:

- Sidebar: `bg-[#0b1320] text-[#c8d4e6]`
- Page: `bg-[#eef3f8]`
- Cards: `rounded-xl border border-slate-200/80 bg-white/95 shadow-[0_18px_40px_rgba(15,23,42,.08)]`
- Hero: `rounded-[28px] border border-cyan-100/80 bg-[linear-gradient(...)]`
- Active nav: `bg-cyan-400/10 text-white ring-1 ring-cyan-300/20`
- Primary button: `bg-[#020617] text-white hover:bg-[#0b1320]`

## Applying to Existing Agent Pages

When redesigning a sub-agent page:

1. Keep the page's business workflow and data contract unchanged.
2. Replace visual shell, spacing, cards, tags, buttons, and status treatment with this skill.
3. Do not borrow colors or component styles from that sub-agent's current page.
4. Keep dense business information, but wrap it in the platform's white card system.
5. Validate against the main platform screenshot, not against the original sub-agent page.

## Verification Checklist

Run this checklist before considering a generated page done:

- It looks like the 智慧矿山智能体平台 main page, not like a sub-agent legacy page.
- Desktop uses dark shell + light workspace.
- Mobile has no horizontal overflow at 390px.
- Button text remains horizontal; no Chinese character vertical stacking.
- Status colors do not overpower blue/cyan as the primary identity.
- Tables become readable stacked cards on mobile, or have an intentional scroll container.
- Only one icon system is used; fallback icons are local line icons.
- No `.env`, backend endpoint, token, or production publishing dependency is introduced.
