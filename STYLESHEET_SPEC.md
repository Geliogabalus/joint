# JointJS Stylesheet Specification

---

## Table of Contents

- [Design Palette](#design-palette)
- [Paper and Paper Scroller](#paper-and-paper-scroller)
  - [Border and Background](#border-and-background)
  - [Grid](#grid)
- [Elements](#elements)
- [Links](#links)
  - [Line](#line)
  - [State Variants](#state-variants)
  - [Label](#label)
- [Ports](#ports)
  - [Body](#body)
  - [State Variants](#state-variants-1)
  - [Label](#label-1)
- [Shape Tools](#shape-tools)
  - [Boundary](#boundary)
  - [Control](#control)
- [Link Tools](#link-tools)
  - [Anchor](#anchor)
  - [Arrowhead](#arrowhead)
  - [Segments](#segments)
  - [Vertices](#vertices)
- [Navigator](#navigator)
- [Stencil](#stencil)
- [Selection](#selection)
- [Snaplines](#snaplines)
- [Halo](#halo)
- [Free Transform](#free-transform)
  - [State Variants](#state-variants-2)
- [Stack Layout](#stack-layout)
- [Tree Layout](#tree-layout)
- [Interactions](#interactions)
- [Icons](#icons)

---

## Design Palette

Colors and other style values used across the diagramming UI. Define these as CSS custom properties and reference them from component variables.

### Colors

| Light | Dark | Variable | Light Value | Dark Value | Description |
|-------|------|----------|-------------|------------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#4dabf7;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-primary` | `#1971c2` | `#4dabf7` | Primary accent — selection, active links, focused handles |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#1e1e2e;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-primary-contrast` | `#ffffff` | `#1e1e2e` | Text / icon color on primary-colored backgrounds |
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#69db7c;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-success` | `#2f9e44` | `#69db7c` | Valid state — connectable ports, valid drop targets |
| <span style="display:inline-block;width:16px;height:16px;background:#e03131;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#ff6b6b;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-danger` | `#e03131` | `#ff6b6b` | Invalid / error state — rejected drops, validation errors |
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#c0c0d8;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-tool` | `#33334f` | `#c0c0d8` | Tool handle fill — link and element manipulation handles |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#1e1e2e;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-tool-contrast` | `#ffffff` | `#1e1e2e` | Contrast stroke on tool handles |
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-text` | `#495057` | `#ced4da` | Default text and stroke color on diagram elements |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-border` | `#ced4da` | `#495057` | Panel and container borders |
| <span style="display:inline-block;width:16px;height:16px;background:#e9ecef;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#2c2c3e;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-border-subtle` | `#e9ecef` | `#2c2c3e` | Subtle separators and secondary borders |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#1e1e2e;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-surface` | `#ffffff` | `#1e1e2e` | Component panel backgrounds, handle fills |
| <span style="display:inline-block;width:16px;height:16px;background:#f8f9fa;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#141420;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-canvas` | `#f8f9fa` | `#141420` | Paper scroller background |
| <span style="display:inline-block;width:16px;height:16px;background:#d0d7de;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | <span style="display:inline-block;width:16px;height:16px;background:#2c2c3e;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `--color-grid` | `#d0d7de` | `#2c2c3e` | Grid dot / line color |

### Border Radius

| Variable | Value | Description |
|----------|-------|-------------|
| `--radius-sm` | `2px` | Small — label borders, viewport frames |
| `--radius-md` | `4px` | Medium — tool handles, preview boxes, selection frames |
| `--radius-lg` | `6px` | Large — info boxes, halo boxes, resize handles |

### Spacing

| Variable | Value | Description |
|----------|-------|-------------|
| `--space-xs` | `2px` | Extra-small — highlighter padding, label text padding |
| `--space-sm` | `4px` | Small — extras rect padding, handle insets |
| `--space-md` | `6px` | Medium — halo padding, free-transform border offset |
| `--space-lg` | `10px` | Large — boundary tool padding |

---

## Paper and Paper Scroller

The main SVG rendering surface.

### Border and Background

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `paper-background` | `var(--color-surface)` | Paper background fill |
| <span style="display:inline-block;width:16px;height:16px;background:#e9ecef;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `paper-border-color` | `var(--color-border-subtle)` | Paper border color |
| | `paper-border-style` | `solid` | Paper border style |
| | `paper-border-width` | `1px` | Paper border width |
| | `paper-box-shadow` | `0 3px 5px rgba(0, 0, 0, 0.3)` | Paper box shadow |
| <span style="display:inline-block;width:16px;height:16px;background:#f8f9fa;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `paper-scroller-background-color` | `var(--color-canvas)` | Paper scroller background color if the [paper is not in infinite mode](https://www.jointjs.com/demos/infinite-paper-vs-sheets) |

### Grid

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| | `paper-grid-type` | `dot` | Grid type |
| <span style="display:inline-block;width:16px;height:16px;background:#d0d7de;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `paper-grid-color` | `var(--color-grid)` | Dot / line grid color |
| | `paper-grid-size` | `10` | Grid cell size |
| | `paper-grid-thickness` | `1` | Grid line / dot thickness |

---

## Elements

TBD

---

## Links

### Line

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-color` | `var(--color-text)` | Default link line color |
| | `link-width` | `2px` | Default link line width |
| | `link-pattern` | `none` | Dash pattern (`none`, `5,5`, etc.) |
| | `link-target-marker` | `arrow` | Target marker type |
| | `link-source-marker` | `none` | Source marker type |

### State Variants

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-hover-color` | `var(--color-primary)` | Line color when hovered |
| | `link-hover-width` | `3px` | Line width when hovered |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-selected-color` | `var(--color-primary)` | Line color when selected |
| | `link-selected-width` | `3px` | Line width when selected |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-connecting-color` | `var(--color-primary)` | Line color when connecting new link |
| | `link-connecting-width` | `3px` | Line width when connecting new link |

### Label

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-label-background-color` | `var(--color-surface)` | Label background rect fill |
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-label-color` | `var(--color-text)` | Label text color |
| | `link-label-font-size` | `14px` | Label font size |
| | `link-label-font-family` | `Arial, sans-serif` | Label font family |
| | `link-label-background-padding` | `var(--space-xs) var(--space-sm)` | Label text padding |
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-label-border-color` | `var(--color-text)` | Label border color |
| | `link-label-border-width` | `1px` | Label border width |
| | `link-label-border-radius` | `var(--radius-sm)` | Label border radius |

---

## Ports

Ports on elements.

### Body

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-color` | `var(--color-surface)` | Port shape fill |
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-border-color` | `var(--color-text)` | Port shape border |
| | `port-body-border-width` | `1.5px` | Port border width |

### State Variants

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-hover-color` | `var(--color-success)` | Fill when hovered (connectable) |
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-border-hover-color` | `var(--color-success)` | Border color when hovered (connectable) |
| | `port-body-hover-border-width` | `2px` | Border width when hovered (connectable) |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-connecting-color` | `var(--color-primary)` | Fill when a link is in the process of connecting |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-border-connecting-color` | `var(--color-primary)` | Border color when a link is in the process of connecting |
| | `port-body-connecting-border-width` | `2px` | Border width when a link is in the process of connecting |

### Label

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-label-color` | `var(--color-text)` | Label text color |
| | `port-label-font-size` | `14px` | Label font size |
| | `port-label-font-family` | `Arial, sans-serif` | Label font family |

---

## Shape Tools

Interactive handles rendered on top of selected shapes.

### Boundary

A dashed rectangle outline drawn around the bounding box of a selected shape.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-boundary-color` | `var(--color-tool)` | Boundary rect stroke color |
| | `tool-boundary-width` | `0.5` | Boundary rect stroke width |
| | `tool-boundary-pattern` | `5, 5` | Boundary rect dash pattern |
| | `tool-boundary-border-radius` | `var(--radius-md)` | Boundary rect corner radius |
| | `tool-boundary-padding` | `var(--space-lg)` | Padding between shape bbox and boundary rect |

### Control

A draggable circular handle used for custom element controls (e.g. corner-radius sliders). Shows a dashed reference rectangle around the target sub-element during a drag.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-control-color` | `var(--color-tool)` | Handle circle fill color |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-control-border-color` | `var(--color-tool-contrast)` | Handle circle stroke color |
| | `tool-control-border-width` | `2` | Handle circle stroke width |
| | `tool-control-radius` | `6` | Handle circle radius |
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-control-extras-color` | `var(--color-tool)` | Extras (reference) rect stroke shown while dragging |
| | `tool-control-extras-pattern` | `2, 4` | Extras rect dash pattern |
| | `tool-control-extras-width` | `1` | Extras rect stroke width |
| | `tool-control-extras-radius` | `var(--radius-md)` | Extras rect corner radius |
| | `tool-control-extras-padding` | `var(--space-sm)` | Padding between target sub-element bbox and extras rect |

## Link Tools

Interactive handles rendered on a selected link.

### Anchor

Draggable handle at the source or target endpoint of a link. Shows a filled circle whose style changes depending on whether a custom anchor is set. A dashed restriction area rectangle is revealed during a drag.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-anchor-color` | `var(--color-tool)` | Default anchor circle fill (no custom anchor) |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-anchor-border-color` | `var(--color-tool-contrast)` | Default anchor circle stroke |
| | `tool-anchor-border-width` | `2` | Default anchor stroke width |
| | `tool-anchor-radius` | `6` | Default anchor circle radius |
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-anchor-area-border-color` | `var(--color-tool)` | Restriction area rect stroke (shown during drag) |
| | `tool-anchor-area-border-width` | `1` | Restriction area rect stroke width |
| | `tool-anchor-area-border-pattern` | `2, 4` | Restriction area rect dash pattern |
| | `tool-anchor-area-border-radius` | `var(--radius-md)` | Restriction area rect corner radius |

### Arrowhead

A draggable arrowhead marker placed at the source (`ratio: 0`) or target (`ratio: 1`) end of a link. Dragging reconnects the link to another element.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-arrowhead-fill` | `var(--color-tool)` | Arrowhead path fill color |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-arrowhead-stroke` | `var(--color-tool-contrast)` | Arrowhead path stroke color |
| | `tool-arrowhead-stroke-width` | `2` | Arrowhead stroke width |

### Segments

Draggable rectangular handles placed at the midpoint of each orthogonal segment. A perpendicular guide line connects the handle back to the link.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-segment-color` | `var(--color-tool)` | Segment handle rect fill |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-segment-border-color` | `var(--color-tool-contrast)` | Segment handle rect stroke |
| | `tool-segment-border-width` | `2` | Segment handle rect stroke width |
| | `tool-segment-width` | `20` | Segment handle rect width |
| | `tool-segment-height` | `8` | Segment handle rect height |
| | `tool-segment-border-radius` | `var(--radius-md)` | Segment handle rect corner radius |
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-segment-line-color` | `var(--color-tool)` | Guide line stroke connecting handle to link |
| | `tool-segment-line-width` | `2` | Guide line stroke width |

### Vertices

Circular handles placed at each bend-point (vertex) of a link. Double-clicking removes a vertex. Clicking the invisible overlay path adds a new vertex.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334f;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-vertex-color` | `var(--color-tool)` | Vertex handle circle fill |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-vertex-border-color` | `var(--color-tool-contrast)` | Vertex handle circle stroke |
| | `tool-vertex-border-width` | `2` | Vertex handle stroke width |
| | `tool-vertex-radius` | `6` | Vertex handle circle radius |

## Navigator

The minimap panel.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-background-color` | `var(--color-surface)` | Navigator background |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-border-color` | `var(--color-border)` | Navigator border |
| | `navigator-border-width` | `1px` | Navigator border width |
| | `navigator-box-shadow` | `0 3px 5px rgba(0, 0, 0, 0.3)` | Navigator box shadow |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-viewport-border-color` | `var(--color-border)` | Navigator viewport border color |
| | `navigator-viewport-border-width` | `1px` | Navigator viewport border width |
| | `navigator-viewport-border-pattern` | `none` | Navigator viewport border dash pattern |
| | `navigator-viewport-border-radius` | `var(--radius-sm)` | Navigator viewport border radius |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-default-link-color` | `var(--color-border)` | Navigator default link color |
| | `navigator-default-link-width` | `1px` | Navigator default link width |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-default-element-color` | `var(--color-border)` | Navigator default element color |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-default-element-border-color` | `var(--color-border)` | Navigator default element border color |
| | `navigator-default-element-border-width` | `1px` | Navigator default element border width |
| | `navigator-default-element-border-radius` | `var(--radius-sm)` | Navigator default element border radius |

---

## Stencil

The stencil panel and interactions.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| | `stencil-drag-opacity` | `0.7` | Opacity of stencil items when dragging |

## Selection

Multi and single selection box and handles.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `selection-wrapper-color` | `var(--color-primary)` | Multiple selection bounding box color |
| | `selection-wrapper-width` | `1.5px` | Multiple selection bounding box width |
| | `selection-wrapper-border-radius` | `var(--radius-md)` | Multiple selection bounding box border radius |
| | `selection-wrapper-pattern` | `none` | Selection border dash pattern |
| | `selection-wrapper-padding` | `5` | Padding between combined bbox and selection wrapper |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `selection-frame-color` | `var(--color-primary)` | Shape selection bounding box color |
| | `selection-frame-width` | `1.5px` | Shape selection bounding box width |
| | `selection-frame-border-radius` | `var(--radius-md)` | Shape selection bounding box border radius |
| | `selection-frame-pattern` | `none` | Shape selection border dash pattern |
| | `selection-frame-padding` | `5` | Padding between shape bbox and selection frame |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `selection-lasso-fill-color` | `var(--color-primary)` | Selection lasso fill color |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `selection-lasso-border-color` | `var(--color-primary)` | Selection lasso border color |
| | `selection-lasso-border-width` | `1.5px` | Selection lasso border width |
| | `selection-lasso-border-radius` | `var(--radius-md)` | Selection lasso border radius |
| | `selection-lasso-border-pattern` | `none` | Selection lasso border dash pattern |

---

## Snaplines

Snaplines styles

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `snaplines-horizontal-color` | `var(--color-primary)` | Horizontal snapline color |
| | `snaplines-horizontal-width` | `1px` | Horizontal snapline stroke width |
| | `snaplines-horizontal-pattern` | `5, 5` | Horizontal snapline dash pattern |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `snaplines-vertical-color` | `var(--color-primary)` | Vertical snapline color |
| | `snaplines-vertical-width` | `1px` | Vertical snapline stroke width |
| | `snaplines-vertical-pattern` | `5, 5` | Vertical snapline dash pattern |

---

## Halo

Halo styles for element highlighting.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| | `halo-padding` | `var(--space-md)` | Halo padding |

---

## Free Transform

Free transform handles and bounding box. Here all sizes are in HTML pixels (not scaled by the paper zoom level).

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| | `free-transform-border-padding` | `var(--space-md)` | Free transform border padding |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-border-color` | `var(--color-primary)` | Free transform bounding box color |
| | `free-transform-border-width` | `1.5px` | Free transform bounding box width |
| | `free-transform-border-pattern` | `none` | Free transform bounding box dash pattern |
| | `free-transform-handle-size` | `6px` | Free transform handle size |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-border-color` | `var(--color-primary)` | Free transform handle border color |
| | `free-transform-handle-border-width` | `2px` | Free transform handle border width |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-background-color` | `var(--color-surface)` | Free transform handle background color |

### State Variants

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-hover-background-color` | `var(--color-success)` | Free transform handle background color when hovered |
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-hover-border-color` | `var(--color-success)` | Free transform handle border color when hovered |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-active-background-color` | `var(--color-primary)` | Free transform handle background color when active (dragged) |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-active-border-color` | `var(--color-primary)` | Free transform handle border color when active (dragged) |

## Stack Layout

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `stack-layout-preview-color` | `var(--color-success)` | Color of a stack layout preview position |
| | `stack-layout-preview-width` | `2px` | Border width of a stack layout preview position |
| <span style="display:inline-block;width:16px;height:16px;background:#e03131;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `stack-layout-preview-invalid-color` | `var(--color-danger)` | Color of a stack layout invalid preview position |
| | `stack-layout-preview-invalid-width` | `2px` | Border width of a stack layout invalid preview position |
| | `stack-layout-drag-opacity` | `0.7` | Opacity of a stack layout element when being dragged |

## Tree Layout

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| | `tree-layout-preview-opacity` | `0.5` | Opacity of a tree layout preview background |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tree-layout-preview-background-color` | `var(--color-primary)` | Color of a tree layout preview background |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tree-layout-preview-border-color` | `var(--color-primary)` | Color of a tree layout preview border |
| | `tree-layout-preview-border-width` | `2px` | Border width of a tree layout preview |
| | `tree-layout-preview-border-radius` | `var(--radius-md)` | Border radius of a tree layout preview |
| | `tree-layout-preview-border-pattern` | `none` | Border dash pattern of a tree layout preview |
| <span style="display:inline-block;width:16px;height:16px;background:#e03131;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tree-layout-preview-invalid-border-color` | `var(--color-danger)` | Color of a tree layout invalid preview border |
| <span style="display:inline-block;width:16px;height:16px;background:#e03131;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tree-layout-preview-invalid-background-color` | `var(--color-danger)` | Color of a tree layout invalid preview background |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tree-layout-parent-highlight-background-color` | `var(--color-primary)` | Color of parent highlight background when previewing a tree layout position |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tree-layout-parent-highlight-border-color` | `var(--color-primary)` | Color of parent highlight border when previewing a tree layout position |
| | `tree-layout-parent-highlight-border-width` | `2px` | Border width of parent highlight when previewing a tree layout position |
| | `tree-layout-parent-highlight-border-radius` | `var(--radius-md)` | Border radius of parent highlight when previewing a tree layout position |
| | `tree-layout-parent-highlight-border-pattern` | `none` | Border dash pattern of parent highlight when previewing a tree layout position |

## Interactions

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `interactions-connection-candidate-highlighter-color` | `var(--color-success)` | Color of candidate element highlighter when connecting |
| | `interactions-connection-candidate-highlighter-width` | `2px` | Border width of candidate element highlighter when connecting |
| | `interactions-connection-candidate-highlighter-pattern` | `none` | Border dash pattern of candidate element highlighter when connecting |
| | `interactions-connection-candidate-highlighter-padding` | `var(--space-xs)` | Padding of candidate element highlighter when connecting |
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `interactions-embedding-container-highlighter-color` | `var(--color-success)` | Color of container element highlighter when embedding |
| | `interactions-embedding-container-highlighter-width` | `2px` | Border width of container element highlighter when embedding |
| | `interactions-embedding-container-highlighter-pattern` | `none` | Border dash pattern of container element highlighter when embedding |
| | `interactions-embedding-container-highlighter-padding` | `var(--space-xs)` | Padding of container element highlighter when embedding |

## Icons

- Rotate
- Resize
- Remove
- Fork
- Connect
- Clone
- Clone and connect
- Break connections
