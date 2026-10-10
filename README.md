# Image PPT to Editable PPT

A Codex skill for rebuilding image-based PowerPoint slides, rasterized PDFs, and slide images as editable PPTX files while preserving their visual design.

## What it does

- Recreates text as native text boxes, tables as editable tables or aligned grids, and diagrams as shapes and connectors.
- Rebuilds standard charts when their data can be recovered reliably.
- Preserves photos, textured artwork, and other suitable raster assets.
- Matches the source slide size, wording, geometry, layering, and styling.
- Renders every reconstructed slide for comparison and checks that reconstructed objects remain editable.
- Flags uncertain OCR and labels estimated chart data in speaker notes.

## Installation

Download or clone this repository into a folder named `image-ppt-to-editable-ppt` inside your configured Codex skills directory. Keep the complete directory structure:

```text
<skills-directory>/image-ppt-to-editable-ppt/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    └── reconstruction-brief.md
```

## Requirements

This skill delegates PPTX authoring, rendering, and validation to the `presentations` skill. Install or enable that skill and its required runtime separately. It is not bundled in this repository.

Provide a PPTX, PDF, or one image per slide. Higher-resolution source material, original fonts, and chart data improve reconstruction fidelity.

## Usage

Attach your source slides and ask Codex:

```text
Use $image-ppt-to-editable-ppt to rebuild these slides as an editable PPTX.
Preserve the supplied design and wording, reconstruct text and diagrams as native
PowerPoint objects, and identify any intentionally retained raster assets.
```

Example in Chinese:

```text
使用 $image-ppt-to-editable-ppt 将这份图片型 PPT 重建为可编辑 PPTX。
保持原始设计和文字，将文本、表格和流程图重建为原生对象，说明保留的图片素材。
```

## Files

| File | Purpose |
|---|---|
| [SKILL.md](SKILL.md) | Reconstruction workflow, fidelity rules, and verification requirements |
| [agents/openai.yaml](agents/openai.yaml) | Display name, description, and default prompt |
| [references/reconstruction-brief.md](references/reconstruction-brief.md) | Reusable prompt, acceptance criteria, and chart-data handling |

The deliverable is a new editable PPTX. Reconstruction accuracy depends on source legibility; unreadable chart data must not be invented.
