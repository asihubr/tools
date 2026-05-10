# Repository conventions

This repo (`asihubr/tools`) is a collection of tiny single-page web apps published via GitHub Pages. Keep things buildless: plain HTML/CSS/JS, no compilation or transpilation, CDN-only dependencies if any.

## Project layout

- Each tool lives in its **own folder** at the repo root, with an `index.html` as the entry point. Use a short, kebab-case folder name (e.g. `color-mixer/`, `unit-converter/`).
- The **root `index.html`** is the launcher: it lists every tool as a card linking to `./<tool-folder>/`.

## Tool UI conventions

Every tool's `index.html` reuses the same chrome so the collection feels like one product:

1. **Home button (top-left)** — Every tool has a fixed `🏠` link in the top-left corner pointing to `../`. Style it as a white circle (~44px desktop, ~38px mobile) with `--shadow-sm`, matching the existing pastel button language. Use `position: fixed; top: 12px; left: 12px; z-index: 60;`.
2. **Centered tool name** — The tool's `<h1>` is visually centered in the header. Tool-specific top-row controls (language switcher, counters, etc.) live as fixed elements in the **top-right** corner so they don't push the title off-center; bigger control clusters drop to a row below the title.
3. **Pastel/Fredoka style** — Reuse the launcher's CSS variables (`--bg-1`, `--bg-2`, `--ink`, `--shadow`, `--shadow-sm`), the radial-gradient background, and the Fredoka font.

When you add a new tool, follow these unless the user explicitly asks for something different.

## When adding a new tool

Every time you create a new tool, you MUST:

1. Put all of its files in a new folder at the repo root (e.g. `/<tool-name>/index.html`). Never drop a tool's files in the repo root.
2. Update the root `/index.html` to add a new card for the tool inside the `.grid` block. Match the existing card markup (emoji, `<h2>` title, short `<p>` description, `href="./<tool-folder>/"`).
3. Keep the launcher's styling consistent across tools — the existing Fredoka + pastel-gradient look is the house style; reuse it unless the user asks for something different.

## When removing or renaming a tool

Also update the root `/index.html` to remove or rename the corresponding card.

## After merging a PR

Always delete the PR's source branch (both remote and local) once it's merged. Don't leave merged feature branches lying around.
