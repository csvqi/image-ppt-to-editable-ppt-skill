---
name: image-ppt-to-editable-ppt
description: Rebuild image-based, PDF-rasterized, or Notebook-generated PowerPoint slides as editable PPTX files while preserving the supplied visual design. Use when text, diagrams, tables, or charts in a slide image must become native editable PowerPoint objects.
---

# Image PPT to Editable PPT

Reconstruction is not a file-format conversion: treat every source slide as a visual reference and recreate the editable structure beneath it. Preserve the source input and export a new PPTX.

Use the `presentations` skill for all PPTX authoring, rendering, and validation. Follow the visual reference route in that skill; a supplied image establishes the design direction, even when no editable source deck exists.

## Intake and route selection

- Accept a PPTX, PDF, or one image per slide. Prefer the highest-resolution source available; request the original PPTX/PDF, font files, and chart data if they exist.
- Match the source slide size and aspect ratio before laying out elements.
- For each element, choose the most editable faithful representation:
  - Text, labels, dates, and footers → native text boxes after careful OCR/transcription.
  - Tables → native PowerPoint tables or aligned text/shape grids.
  - Basic process diagrams, timelines, and callouts → native shapes, connectors, and text.
  - Standard charts with legible axes/data labels → native PowerPoint charts; use source data if available.
  - Photos, textured artwork, maps, or dense non-semantic decoration → retained raster assets are allowed.
- Do not use a full-slide screenshot as the delivered slide when the foreground can be reconstructed. A hybrid slide may retain only an unobtrusive background or non-editable artwork.

## Reconstruction principles

- Rebuild the slide hierarchy: background first, then connectors, shapes, and finally text. Put connectors behind the cards and labels they link.
- Match visible geometry before fine styling: slide margins, major anchors, card sizes, and baseline alignment matter more than a nominal font match.
- Maintain the source wording, capitalization, units, dates, and qualifiers. Flag uncertain OCR rather than silently correcting or inventing content.
- Never infer precise underlying chart data from an unreadable image. If it cannot be recovered with confidence, preserve the image or create an approximate editable graphic that is clearly marked in speaker notes as estimated.
- Do not add or remove source-brand elements, watermarks, or logos unless the user explicitly asks; their legal status cannot be inferred from an image.

## Verification and delivery

- Render every reconstructed slide and compare it with its reference at full-slide size.
- Fix clipping, unintended overlap, text wrapping, bad connector layering, scale mismatches, and obvious color/spacing errors.
- Confirm that text, tables, diagrams, and reconstructed charts are native PowerPoint objects, not flattened into a screenshot.
- Deliver the editable PPTX and briefly distinguish native reconstructed elements from any intentionally retained raster assets.

For reusable prompt language, detailed acceptance criteria, and chart-data handling, read [references/reconstruction-brief.md](references/reconstruction-brief.md).
