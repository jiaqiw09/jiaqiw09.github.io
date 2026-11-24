---
name: infra-html-diagrams
description: Create, refresh, review, and publish HTML technical diagrams and file navigation on infra杂谈. Use for diagram redraws, multi-rank flows, visual corrections, and new or existing notes in this GitHub Pages repository.
---

# Infra HTML diagrams

## Use the Ulysses SP layout as the reference

- Start from `notes/ulysses-sp/index.html`. Use compact, visually separated modules that each explain one concept, example, or operation. Put the diagram, labels, formulas, code, and the explanation they depend on in the same module. Keep the detailed technical content.
- Arrange each module according to the relationship it explains. Use left and right positions for comparisons, Rank ownership, or horizontal data movement, and upper and lower positions for local steps or levels. Keep the grouping and reading order of the reference. Fit the diagram between adjacent modules with consistent gaps and enough room around the arrows.
- For multi-rank flows, keep each numbered stage together with its lanes and connectors. Use `notes/fsdp2-ep/index.html` for the Rank comparison and `notes/gpu-rdma/index.html` for topology and linked steps. Preserve their multi-column geometry at the site's content-pane width. Use `.diagram-scroll` from `assets/reader.css` to let wide modules scroll horizontally when their columns would otherwise get cramped.

## Preserve content and connections

- For a redraw, preserve the supplied source's section and lane order, labels, formulas, code, tensor shapes, examples, and conclusions. Treat a technical correction as a separate requested edit.
- Before changing arrows, inventory each connector in the original reference by stage, endpoints, direction, and line style. Include arrows inside cards, dashed comparison lines, and crossed arrows. Preserve their count, route, and direction. A crossed four-headed connector stays crossed.
- When fixing a redraw, compare against the original source as well as the current HTML. Check each connector at the card or row where it belongs, including its spacing and endpoints.

## Apply the site palette

- Use `assets/reader.css` for the gray-white page, charcoal text, fine dividers, and muted blue links. Keep this page palette independent from the colors inside diagrams.
- Use pale fills inside diagrams to group related content. Use muted blue for general flow and Rank data, soft green for calculation or output where it fits, amber for caveats, and muted coral for highlighted communication steps where the reference uses a separate color. Preserve established color meanings such as the purple RDMA network. Pair each meaningful color with a label, shape, line style, or position.
- Give equivalent Rank cards the same tint. Use labels and lane positions to identify ownership. Use an opaque white canvas for a standalone PNG export when requested.

## Integrate and verify on the site

- Place a new chapter at `notes/<chapter>/index.html` and use the shared reader stylesheet. Add its file name under the appropriate collapsible folder in the left catalog. Folder depth defines the tree. Keep in-article headings in the right reading pane.
- Verify the complete note at its direct URL and when opened from the homepage. At desktop width, verify the side-by-side layouts, all connector directions, and readable label spacing. At narrow widths, verify that wide modules pan within their own region, text and headings fit the page, and the diagrams retain their original left/right and top/bottom relationships.
- Check that the current file is highlighted and that existing chapter links still resolve. Publish when requested. Keep this skill under `.agents/skills/` outside the site's catalog.
