---
name: infra-html-diagrams
description: Create, redraw, review, and publish self-contained HTML technical diagrams on infra杂谈. Use for diagrams reproduced from an image, multi-rank communication flows, visual corrections, and new diagram chapters in this GitHub Pages repository.
---

# Infra HTML diagrams

## Preserve content and connections

- For a redraw, preserve the supplied source's section and lane order, labels, formulas, code, tensor shapes, examples, and conclusions. Treat a technical correction as a separate requested edit.
- Before changing arrows, inventory each connector in the original reference by stage, endpoints, direction, and line style. Include small arrows inside a card, dashed comparison lines, and crossed arrows. Preserve their count, route, and direction. A crossed four-headed connector stays crossed. Parallel arrows represent a different drawing.
- When fixing a redraw, compare against the original source as well as the current HTML. Verify each arrow at the card or row where it belongs.

## Group related content into cards

- Follow the section-card hierarchy used in `notes/gpu-rdma/index.html` and `notes/ulysses-sp/index.html`. Give major sections their own white cards with light borders, rounded corners, and enough space between sections.
- For a multi-rank workflow, put each numbered step in one outer card. Keep the operation title in its header and the corresponding lanes, explanations and arrows together below it. Use inner cards for distinct examples or rank data.
- Use one step number per group and leave visual separation around arrows. Keep labels, code and examples in their original stage.

## Use a restrained palette

- Keep the HTML diagram and its PNG export on an opaque white canvas (`#fff`). Use dark navy text, muted blue for arrows and key labels, and blue-gray borders and tints.
- Use the same pale tint for equivalent rank cards, with rank names, lane positions, and labels identifying ownership. Use line styles or lightness to distinguish tokens or stages. Add another hue only when the supplied source relies on that color to encode information or the user requests it.
- Draw connectors with consistent geometric shafts and arrowheads. Reserve space between the connected cards, and align the arrows to their ends. Keep labels and badges readable on narrow screens.

## Verify and publish

- Use self-contained HTML with inline styles. Compare the rendered text and numeric examples with the source, and inspect every connector at desktop width, at the site's content-pane width, and when lanes stack. Export the PNG from the final HTML and check that its background is white.
- Put the chapter at `notes/<chapter>/index.html`. For new chapters, add an entry to the left catalog on the homepage. Publish the HTML and share a separate PNG when requested.
- Keep this skill under `.agents/skills/` outside the site's catalog and published pages.
