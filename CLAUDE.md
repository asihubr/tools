# Repository conventions

This repo (`asihubr/tools`) is a collection of tiny single-page web apps published via GitHub Pages. Keep things buildless: plain HTML/CSS/JS, no compilation or transpilation, CDN-only dependencies if any.

## Project layout

- Each tool lives in its **own folder** at the repo root, with an `index.html` as the entry point. Use a short, kebab-case folder name (e.g. `color-mixer/`, `unit-converter/`).
- The **root `index.html`** is the launcher: it lists every tool as a card linking to `./<tool-folder>/`.

## When adding a new tool

Every time you create a new tool, you MUST:

1. Put all of its files in a new folder at the repo root (e.g. `/<tool-name>/index.html`). Never drop a tool's files in the repo root.
2. Update the root `/index.html` to add a new card for the tool inside the `.grid` block. Match the existing card markup (emoji, `<h2>` title, short `<p>` description, `href="./<tool-folder>/"`).
3. Keep the launcher's styling consistent across tools — the existing Fredoka + pastel-gradient look is the house style; reuse it unless the user asks for something different.

## When removing or renaming a tool

Also update the root `/index.html` to remove or rename the corresponding card.
