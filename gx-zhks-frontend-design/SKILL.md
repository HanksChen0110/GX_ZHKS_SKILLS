---
name: gx-zhks-frontend-design
description: "Use this skill when the user explicitly asks for gx-zhks frontend design, gx-zhks-frontend-design, 智慧矿山智能体平台风格, or to redesign a smart-mine agent page using the unified 智慧矿山智能体平台 design system. Do not trigger for generic UI work."
version: 1.1.0
allowed-tools: [Read, Write, Edit, Glob, Grep]
---

# gx-zhks-frontend-design

This skill applies the unified frontend design language of the 智慧矿山智能体平台 main page.

Reference source: only `http://125.69.16.175:8015/smart-mine/index.html`.

Do not use the "最近使用" pages or sub-agent systems such as 岩芯识别、申报、边坡监测 as style references. Those pages are future redesign targets, not the design source.

## Design Philosophy

The interface is a mine-operation command center made approachable for business users: a dark, stable navigation shell around a light blue-gray working surface.

Use a calm technical layout, not a marketing landing page. The page should feel like a real platform home: left-side persistent navigation, grid-backed hero stage, recommended capability cards, agent entry cards, clear status chips, and a strong dark action button.

The signature tension is:

- dark navy platform chrome for trust and system weight
- pale mine-blue workspace for readability
- cyan/blue gradients and fine grid lines for intelligent-agent technology
- white rounded cards for operational clarity

## Workflow

1. Declare fonts: use `Inter, PingFang SC, Microsoft YaHei, Helvetica Neue, Arial, sans-serif`.
2. Load `references/visual-craft.md` before visual implementation. This file defines the 1:1 craft layer: page grid, hero grid, inner glass panel, shadows, hover, prompt bar, and sidebar gradient.
3. Apply tokens from `references/tokens.md`.
4. Build layout and components from `references/components.md`.
5. Pick a page pattern from `references/page-patterns.md` before composing business pages.
6. Keep the left navigation visible on desktop; on narrow mobile previews, preserve the dark shell if the target app already has a sidebar, otherwise collapse it into a top bar.
7. For existing React/Vite apps, fix product identity before visual QA: browser title, favicon, app brand text, and sidebar logo must match the product. Never leave Vite/React/default `web` labels or lightning icons.
8. Use only Tabler Icons as the icon kit when icon fonts are available; if unavailable, use the local line-icon fallback in `references/platform-mapping.md`.
9. Verify the result against the main platform, not against the sub-agent pages.

## Core Rules

- The gx completion standard is not just a blue admin page. It must read as: pale grid workspace + dark fixed gradient sidebar + glassy hero/status panel + tactile prompt bar + subtle card micro-motion.
- Use a dark left sidebar: `#0b1320` to `#020617`, active item in translucent cyan.
- On desktop, the left sidebar is persistent navigation: fix it to the viewport and offset the workspace by the same sidebar width. Long pages must scroll on the right while the sidebar remains clickable from top to bottom.
- Use a cool light workspace: `#eef3f8`, `#eff8ff`, `#f4f7fb`.
- Use the page grid from `visual-craft.md`: fixed full-screen 28px grid, very low-opacity slate lines, stronger at the top and masked downward.
- Use hero/status panels with layered blue/cyan washes, 72px vertical grid texture, and an optional centered glass frame when the page is a platform home.
- Use large hero titles with navy-to-cyan gradient text.
- Use white cards with soft shadow, thin cool borders, and 16-24px radius on home/agent cards; use 8-12px radius on dense business pages.
- Use dark primary buttons: near-black navy background, white text, compact height, small arrow icon.
- Use status chips for configured/unconfigured, risk, category, and capability labels.
- Cards that are interactive must use the standard hover: `translateY(-2px)`, cyan border lift, and soft pseudo-element glow. Do not invent larger animations.
- For business pages, keep data dense but organized: filters, tables, upload areas, chat panels, drawers, and step cards should all use the same white-card platform language.
- Keep copy concise and operational. Avoid decorative slogans.
- Business tool pages should feel like a working console, not a landing page: prefer 8-12px card radius, restrained shadows, compact hero/status bands, and readable tables.

## Anti-patterns

- Do not use the visual style of 申报、边坡、岩芯 or other recently used pages as the source.
- Do not turn the platform into a dark full-screen dashboard; the observed main workspace is light.
- Do not use purple-heavy, orange-heavy, beige, or generic SaaS palettes.
- Do not use oversized decorative cards inside cards.
- Do not add stock photos, abstract blobs, or marketing hero illustrations.
- Do not mix icon libraries.
- Do not keep framework starter assets such as Vite favicon, React favicon, page title `web`, or placeholder metadata.
- Do not create a landing page when the task is to build an application page.
- Do not let mobile buttons become vertical text; wrap layout, not individual Chinese characters.

## References

Load these files only as needed:

- `references/visual-craft.md` - 1:1 craft details for grid, shadows, hover, prompt bar, hero layers, sidebar gradient, and visual QA
- `references/tokens.md` - colors, typography, spacing, radius, elevation, motion, icon choices
- `references/components.md` - navigation, hero, cards, status chips, prompt bar, agent entries
- `references/page-patterns.md` - business page patterns for chat, review, monitoring, forms, tables, drawers
- `references/platform-mapping.md` - HTML/CSS and React/Tailwind implementation rules