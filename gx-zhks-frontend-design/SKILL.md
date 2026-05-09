---
name: gx-zhks-frontend-design
description: "Use this skill when the user explicitly asks for gx-zhks frontend design, gx-zhks-frontend-design, 智慧矿山智能体平台风格, or to redesign a smart-mine agent page using the unified 智慧矿山智能体平台 design system. Do not trigger for generic UI work."
version: 1.0.0
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
2. Apply tokens from `references/tokens.md`.
3. Build layout and components from `references/components.md`.
4. Pick a page pattern from `references/page-patterns.md` before composing business pages.
5. Keep the left navigation visible on desktop; on narrow mobile previews, preserve the dark shell if the target app already has a sidebar, otherwise collapse it into a top bar.
6. Use only Tabler Icons as the icon kit when icon fonts are available; if unavailable, use the local line-icon fallback in `references/platform-mapping.md`.
7. Verify the result against the main platform, not against the sub-agent pages.

## Core Rules

- Use a dark left sidebar: `#0b1320` or `#020617`, active item in translucent cyan.
- Use a cool light workspace: `#eef3f8`, `#eff8ff`, `#f4f7fb`.
- Use subtle grid backgrounds in hero or large panels.
- Use large hero titles with navy-to-cyan gradient text.
- Use white cards with soft shadow, thin cool borders, and 16-24px radius.
- Use dark primary buttons: near-black navy background, white text, compact height, small arrow icon.
- Use status chips for configured/unconfigured, risk, category, and capability labels.
- For business pages, keep data dense but organized: filters, tables, upload areas, chat panels, drawers, and step cards should all use the same white-card platform language.
- Keep copy concise and operational. Avoid decorative slogans.

## Anti-patterns

- Do not use the visual style of 申报、边坡、岩芯 or other recently used pages as the source.
- Do not turn the platform into a dark full-screen dashboard; the observed main workspace is light.
- Do not use purple-heavy, orange-heavy, beige, or generic SaaS palettes.
- Do not use oversized decorative cards inside cards.
- Do not add stock photos, abstract blobs, or marketing hero illustrations.
- Do not mix icon libraries.
- Do not create a landing page when the task is to build an application page.
- Do not let mobile buttons become vertical text; wrap layout, not individual Chinese characters.

## References

Load these files only as needed:

- `references/tokens.md` - colors, typography, spacing, radius, elevation, motion, icon choices
- `references/components.md` - navigation, hero, cards, status chips, prompt bar, agent entries
- `references/page-patterns.md` - business page patterns for chat, review, monitoring, forms, tables, drawers
- `references/platform-mapping.md` - HTML/CSS and React/Tailwind implementation rules
