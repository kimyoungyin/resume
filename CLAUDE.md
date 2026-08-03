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
1. Title + links (Service Link / GitHub / Private Repo)
2. Meta: period | team/personal | role
3. One-sentence overview (italic, class `project-desc`)
4. Skills (with versions where possible)
5. Key Achievements (2–3 D-P-S-R bullets)
6. Basic Implementations (bullet list)

## CSS Layout Notes

- Web preview: `max-width: 900px`, responsive padding via `clamp`.
- Print target: A3 (`@page { size: A3 }`), `max-width: 297mm`, tighter spacing overrides via `!important` in the print media query.
- Section headers (`h2`) use `#2563eb` blue with a bottom border.
- Project items are separated by `border-top: 2px solid #e5e7eb` (except the first).
- Skills use a two-column CSS grid: `140px` label + `1fr` value.
