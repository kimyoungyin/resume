# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML/CSS resume for 김영인 (Kim Young-yin), a frontend developer. No build system — the project is two files: `index.html` and `styles.css`. Open `index.html` directly in a browser to preview.

## Content Writing Rules (D-P-S-R Structure)

All project achievement bullets must follow the **Domain-Problem-Solution-Result** formula:

```
[Domain] {Context/Problem} → {Action/Solution} → {Result/Impact}
```

Example:
> [인증] 토큰 만료 시 중복 요청으로 인한 세션 끊김 문제 → Singleton Promise 패턴 도입으로 호출 단일화 → 인증 안정성 확보 및 불필요한 API 호출 50% 절감

### Content principles
- Every achievement must include a **quantified result** (e.g., LCP 4.69s → 2.81s, 80% improvement).
- Always explain **why** (user impact, UX, SEO score, etc.) — never just "implemented X."
- Only describe the author's personal contribution, not team-wide achievements.
- Include a "Basic Implementations" section per project to list standard skills explicitly.

### Project structure per entry
1. `.project-head` — title + links (Service Link / GitHub / Private Repo), meta line (`회사 · 기간 · 팀 구성 · 역할`, `·` separated), one-sentence overview (`.project-desc`)
2. Skills line (`.project-skills`, with versions where possible) — prefixed by a small `.inline-label`
3. `Key Achievements` (`.block-label`) + 2–3 D-P-S-R bullets
4. `Basic Implementations` (`.block-label`) + bullet list

## CSS Layout Notes

The document is a single A3-width sheet (`.sheet`, `297mm`) with a `18mm` inset, laid out as a
two-column grid per section: a `40mm` label column (`h2`) plus the content column (`.section-body`).

- Typography: Pretendard Variable (jsDelivr CDN), sizes in `pt`, spacing in `mm` so screen and print agree.
- Accent blue is `#1e40af` (`--accent`); all palette values live as custom properties on `:root`.
- Section headers (`h2`) are small uppercase labels with `0.18em` tracking — not underlined titles.
- Sections are separated by `border-top: 1px solid #e4e7ec` (`.doc-section`, except the first);
  the header rule is `2.5px solid #191d24`.
- Project items are separated by the same `1px` rule; `.project-head` is `break-inside/after: avoid`
  so a project's title block never lands alone at the bottom of a page.
- Skills use a two-column grid (`dl.skills`): `36mm` label + `1fr` value.
- Print target: A3 (`@page { size: A3; margin: 18mm }`); at print the sheet drops its own padding,
  shadow, and width cap so the page box owns the margins.
- Screen-only breakpoints at `1100px` / `820px` / `520px` collapse the label columns to a single column.
