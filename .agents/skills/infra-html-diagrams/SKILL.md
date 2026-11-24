---
name: infra-html-diagrams
description: Create or revise the self-contained HTML technical diagrams on infra杂谈, including reproductions of supplied diagrams, communication flows, and new chapters for this GitHub Pages repository. Use when asked to draw, redraw, or publish an HTML diagram here.
---

# Infra HTML diagrams

## Preserve the source

- When redrawing a supplied diagram, preserve its section order, lane order, labels, formulas, code, shapes, numeric examples, and conclusions. Change their visual presentation only. Treat any technical correction as a separate requested edit.
- For a localized revision, change the requested elements and compare the resulting diagram with the previous version.

## Draw on white

- Give the diagram HTML and its PNG export an opaque white canvas (`#fff`). The site shell may have its own background.
- Use dark navy text and neutral borders. Use blue and green accents with pale tints inside rank cards. For EP, use blue for Rank 0 and green for Rank 1. Use an amber accent for combine or summary blocks when it distinguishes the stage.
- Keep lane headers and their cards aligned. Use real text for technical details and a monospace font for code, indices, and tensor shapes.

## Draw readable arrows

- Draw graphical arrows with CSS geometry in reserved connector space. Use a thin straight shaft and a consistent chevron head. Align each arrow with the cards it connects. Keep arrows clear of labels, badges, and borders.
- Use two parallel arrows pointing in opposite directions for simultaneous sends and receives. For rank diagrams, carry the sender's color through its entire route. Use one arrow for a one-way edge. Keep dashed double-ended connectors for comparison annotations.
- Keep directions explicit in the labels. On narrow widths, stack the lanes in reading order and turn the connector paths to match that order. Check the diagram both as a standalone page and inside the site's narrower content pane.

## Verify and publish

- Keep each diagram in one HTML file with inline styles. Before publishing, render it in a browser and inspect its connector direction, white background, content preservation, and narrow layout. Export a PNG from the same HTML when requested.
- Put the HTML under `notes/<chapter>/index.html`. Add one matching entry in the homepage's left catalog for a new chapter. Publish only the HTML for each chapter unless asked to include other assets.
- Keep this skill in `.agents/skills/` and outside site navigation and published pages.
