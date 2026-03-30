# Agent Guidelines

When working on visual effects, CSS animations, heavy DOM trees, or animation feedback in this project — if you encounter frame drops or receive user feedback about page lag, **consult this guide first**. These are hard-won lessons that must be treated as non-negotiable rules.

## CSS Animation Performance

Applies when the task involves CSS animations or heavy effect layers (glow, text effects, light blades, particles, etc.).

### Never Do

1. **No global filter animations**: Never apply `clip` or `filter`-based frame animations to `document.body` or any large container wrapping many elements (e.g., a full-screen `drop-shadow` during a screen shake). Keep effects strictly scoped to the target component. Once they spread to outer containers, the browser drops the GPU pipeline and falls back to per-frame CPU rasterization.

2. **Avoid extreme blur radii**: Never use very large blur values on `box-shadow` or `text-shadow` (e.g., `120px`, `160px`). Massive Gaussian blur easily exhausts the texture cache on mid-to-low-end devices. Do not stack two expensive filters on the same element. Keep text glow at a restrained range (`40px–60px`) and combine with native color bands.

3. **Do not mix blend modes with heavy blur**: Unless strictly necessary, do not combine `mix-blend-mode: screen` and `filter: blur` on a fast-animating, bright-colored layer (e.g., `#FFFFFF` white).

4. **Prevent GPU texture size overflow**: When using `will-change: transform` or hardware-accelerated large-scale `scale()` animations (e.g., an intro effect at `scale(3)`), be extremely careful about the physical bounding width of the base node. If the node contains long text (e.g., an `(alt)` suffix accidentally rendered) combined with a deep `drop-shadow` outer glow, the GPU pre-allocates a texture box covering the element's maximum bounds at animation start. If that pixel width multiplied by the scale factor exceeds the GPU's texture size limit (e.g., 4096px), the browser immediately demotes it out of hardware acceleration and falls back to CPU rasterization — FPS drops from 60 to single digits.

   To defuse this: strip unnecessary text suffixes before animating (`label.replace(...)`), and cap the scale value (avoid `scale(10)`; `scale(2.2)–scale(3)` already delivers strong visual impact).

### Always Do

For elements about to undergo heavy transforms (especially `scale` or `translate`) or complex glow states — particles, text containers — explicitly promote them to their own GPU layer:

```css
.effect-item {
  will-change: transform, opacity, filter;
  transform: translateZ(0);
}
```

This converts expensive per-frame math into a pure texture scale operation, enabling consistent 60 FPS.

## Git Commit Convention

All commit messages must be written in **English**.

Use **Conventional Commits** format: `type[(scope)]: subject`

### Allowed Types

| Type | When to use |
|---|---|
| `feat` | New sound pack or new feature |
| `fix` | Bug fix or incorrect manifest data |
| `docs` | README or documentation changes |
| `style` | Formatting only, no logic change |
| `refactor` | Restructure without adding/removing functionality |
| `perf` | Performance improvement |
| `test` | Test-related changes |
| `build` | Build system or dependency changes |
| `ci` | CI/CD configuration changes |
| `chore` | Miscellaneous maintenance |
| `revert` | Revert a previous commit |

### Rules

- `type` and optional `scope` must be lowercase
- Subject must be concise and imperative (e.g., `add`, `remove`, `update`)
- No trailing punctuation in the subject line
- Breaking changes: use `!` after type/scope, add `BREAKING CHANGE:` footer

### Examples

```
feat(honor_of_kings): add 90 voice lines for all 6 core CESP categories
fix(ra2_eva_commander): remove establishing-battlefield-control from session.start
feat: add honor_of_kings and ra2_eva_commander sound packs
```
