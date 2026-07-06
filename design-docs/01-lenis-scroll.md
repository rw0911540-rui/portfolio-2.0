# Task 1: Lenis Smooth Scroll

## Goal
Replace current CSS `transform: translateY` page switching with Lenis smooth-scroll for 60fps inertia + snap.

## Current State
- File: `site.html`
- Method: `PageController.goTo()` sets `--current-page` CSS var → `.page-track` does `transform: translateY(calc(var * -100vh))` with 0.72s CSS transition
- Wheel handler: rAF-based accumulation, threshold 60px

## Requirements
1. Introduce Lenis (inline or CDN script tag)
2. Lenis wraps the viewport, pages become scroll sections (not translateY)
3. Snap to nearest page on scroll end
4. Keep keyboard nav (Arrow keys, Home, End)
5. Keep touch support
6. Keep `isTransitioning` lock to prevent double-trigger
7. Dark/light theme must still work
8. Gallery page must still auto-scroll videos

## Reference
- https://github.com/darkroomengineering/lenis
- CDN: `https://cdn.jsdelivr.net/npm/@studio-freight/lenis@latest`

## Code Files
- `site.html` — HTML structure (6 `.page` sections in `.viewport` > `.page-track`)
- PageController class (~line 1320-1390)
