# Reconstruction Brief

Use this brief when a user asks for a repeatable prompt, submits a multi-slide image deck, or requires explicit fidelity criteria.

## Prompt template

```text
Rebuild the supplied image-based presentation as an editable PowerPoint (.pptx).

Use each source page as a visual reference, preserving its slide size, hierarchy,
layout, text, color system, spacing, and visual style. Keep the source files
unchanged and export a new editable PPTX.

Make all readable text, labels, tables, simple diagrams, lines, arrows, and
standard charts native PowerPoint objects. Do not use a complete slide screenshot
as the final slide. Photos, complex illustrations, maps, and non-semantic
background artwork may remain images when rebuilding them would not improve
editability.

For charts, use provided workbook/CSV data whenever available. If the image does
not support reliable recovery of the underlying values, do not invent exact data;
retain the chart as an image or create an explicitly estimated native chart and
record the limitation in speaker notes.

Render and compare every finished slide with the source. Correct clipping,
unintended overlap, text wrapping, color, alignment, and layering before delivery.
```

## Fidelity acceptance checklist

- The slide dimensions and background treatment agree with the reference.
- Titles, body copy, labels, and values can be edited in PowerPoint.
- Repeated cards, bars, and simple drawings use separate native objects.
- Connectors do not obscure labels or pass through unrelated shapes.
- Charts are editable only when their data is known or defensibly transcribed.
- Any retained raster elements are limited to material that is impractical to make editable.
- Uncertain OCR and estimated chart data are disclosed in speaker notes.

## Chart decision rule

| Source condition | Deliverable treatment |
|---|---|
| Workbook, CSV, or reliably readable labels | Native editable chart with verified series and axes |
| Clear chart geometry but incomplete labels | Rebuild as a native visual approximation; add an estimation note |
| Data cannot be read or validated | Retain the chart image; request the source data for later conversion |

## Example: phased roadmap slide

A stair-step roadmap generally decomposes into editable text boxes, white content cards, colored stage rectangles, divider lines, and one native curved connector. A faint architectural or photographic background can remain raster if it does not carry any content the user needs to edit.
