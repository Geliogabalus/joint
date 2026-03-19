# JointJS Stylesheet Specification

---

## Table of Contents

---

## Design Palette

Colors and other style values used across the diagramming UI. These can be defined as CSS custom properties (variables) and referenced in your stylesheet.

---

## Paper and Paper Scroller

The main SVG rendering surface.

### Border and Background

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `paper-background` | `#ffffff` | Paper background fill |
| <span style="display:inline-block;width:16px;height:16px;background:#eee;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `paper-border-color` | `#eee` | Paper border color |
| | `paper-border-style` | `solid` | Paper border style |
| | `paper-border-width` | `1px` | Paper border width |
| | `paper-box-shadow` | `0 3px 5px rgba(0, 0, 0, 0.3)` | Paper box shadow |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `paper-scroller-background-color` | `#ffffff` | Paper scroller background color if the [paper is not in infinite mode](https://www.jointjs.com/demos/infinite-paper-vs-sheets)  |

### Grid

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| | `paper-grid-type` | `dot` | Grid type |
| <span style="display:inline-block;width:16px;height:16px;background:#d0d7de;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `paper-grid-color` | `#d0d7de` | Dot / line grid color |
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
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-color` | `#495057` | Default link line color |
| | `link-width` | `2px` | Default link line width |
| | `link-pattern` | `none` | Dash pattern (`none`, `5,5`, etc.) |
| | `link-target-marker` | `arrow` | Target marker type |
| | `link-source-marker` | `none` | Source marker type |

### State Variants

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-hover-color` | `#1971c2` | Line color when hovered |
| | `link-hover-width` | `3px` | Line width when hovered |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-selected-color` | `#1971c2` | Line color when selected |
| | `link-selected-width` | `3px` | Line width when selected |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-connecting-color` | `#1971c2` | Line color when connecting new link |
| | `link-connecting-width` | `3px` | Line width when connecting new link |

### Label

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-label-background` | `#ffffff` | Label background rect fill |
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `link-label-color` | `#495057` | Label text color |
| | `link-label-font-size` | `14px` | Label font size |
| | `link-label-font-family` | `Arial, sans-serif` | Label font family |
| | `link-label-background-padding` | `2px 4px` | Label text padding |

TODO: more label properties

---

## Ports

Ports on elements.

### Body

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-color` | `#ffffff` | Port shape fill |
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-border-color` | `#495057` | Port shape border |
| | `port-body-border-width` | `1.5px` | Port border width |

### State Variants

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-hover-color` | `#2f9e44` | Fill when hovered (connectable) |
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-border-hover-color` | `#2f9e44` | Fill when hovered (connectable) |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-connecting-color` | `#1971c2` | Fill when a link is in the process of connecting |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-body-border-connecting-color` | `#1971c2` | Fill when a link is in the process of connecting |

### Label

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#495057;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `port-label-color` | `#495057` | Label text color |
| | `port-label-font-size` | `14px` | Label font size |
| | `port-label-font-family` | `Arial, sans-serif` | Label font family |

---

## Shape Tools

Interactive handles rendered on top of selected shapes.

### Boundary

A dashed rectangle outline drawn around the bounding box of a selected shape.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334F;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-boundary-color` | `#33334F` | Boundary rect stroke color |
| | `tool-boundary-width` | `0.5` | Boundary rect stroke width |
| | `tool-boundary-pattern` | `5, 5` | Boundary rect dash pattern |
| | `tool-boundary-padding` | `10` | Padding between shape bbox and boundary rect |

### Control

A draggable circular handle used for custom element controls (e.g. corner-radius sliders). Shows a dashed reference rectangle around the target sub-element during a drag.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334F;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-control-color` | `#33334F` | Handle circle fill color |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-control-border-color` | `#FFFFFF` | Handle circle stroke color |
| | `tool-control-border-width` | `2` | Handle circle stroke width |
| | `tool-control-radius` | `6` | Handle circle radius |
| <span style="display:inline-block;width:16px;height:16px;background:#33334F;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-control-extras-color` | `#33334F` | Extras (reference) rect stroke shown while dragging |
| | `tool-control-extras-pattern` | `2, 4` | Extras rect dash pattern |

## Link Tools

Interactive handles rendered on a selected link.

### Anchor

Draggable handle at the source or target endpoint of a link. Shows a filled circle whose style changes depending on whether a custom anchor is set. A dashed restriction area rectangle is revealed during a drag.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334F;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-anchor-color` | `#33334F` | Default anchor circle fill (no custom anchor) |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-anchor-border-color` | `#FFFFFF` | Default anchor circle stroke |
| | `tool-anchor-border-width` | `2` | Default anchor stroke width |
| | `tool-anchor-radius` | `6` | Default anchor circle radius |
| <span style="display:inline-block;width:16px;height:16px;background:#33334F;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-anchor-area-border-color` | `#33334F` | Restriction area rect stroke (shown during drag) |
| | `tool-anchor-area-border-pattern` | `2, 4` | Restriction area rect dash pattern |

### Arrowhead

A draggable arrowhead marker placed at the source (`ratio: 0`) or target (`ratio: 1`) end of a link. Dragging reconnects the link to another element.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334F;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-arrowhead-fill` | `#33334F` | Arrowhead path fill color |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-arrowhead-stroke` | `#FFFFFF` | Arrowhead path stroke color |
| | `tool-arrowhead-stroke-width` | `2` | Arrowhead stroke width |

### Segments

Draggable rectangular handles placed at the midpoint of each orthogonal segment. A perpendicular guide line connects the handle back to the link.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334F;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-segment-color` | `#33334F` | Segment handle rect fill |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-segment-border-color` | `#FFFFFF` | Segment handle rect stroke |
| | `tool-segment-border-width` | `2` | Segment handle rect stroke width |
| | `tool-segment-width` | `20` | Segment handle rect width |
| | `tool-segment-height` | `8` | Segment handle rect height |
| | `tool-segment-border-radius` | `4` | Segment handle rect corner radius |
| <span style="display:inline-block;width:16px;height:16px;background:#33334F;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-segment-line-color` | `#33334F` | Guide line stroke connecting handle to link |
| | `tool-segment-line-width` | `2` | Guide line stroke width |

### Vertices

Circular handles placed at each bend-point (vertex) of a link. Double-clicking removes a vertex. Clicking the invisible overlay path adds a new vertex.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#33334F;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-vertex-color` | `#33334F` | Vertex handle circle fill |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `tool-vertex-border-color` | `#FFFFFF` | Vertex handle circle stroke |
| | `tool-vertex-border-width` | `2` | Vertex handle stroke width |
| | `tool-vertex-radius` | `6` | Vertex handle circle radius |

## Navigator

The minimap panel.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-background-color` | `#ffffff` | Navigator background |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-border-color` | `#ced4da` | Navigator border |
| | `navigator-border-width` | `1px` | Navigator border width |
| | `navigator-box-shadow` | `0 3px 5px rgba(0, 0, 0, 0.3)` | Navigator box shadow |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-viewport-border-color` | `#ced4da` | Navigator viewport border color |
| | `navigator-viewport-border-width` | `1px` | Navigator viewport border width |
| | `navigator-viewport-border-pattern` | `none` | Navigator viewport border dash pattern |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-default-link-color` | `#ced4da` | Navigator default link color |
| | `navigator-default-link-width` | `1px` | Navigator default link width |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-default-element-color` | `#ced4da` | Navigator default element color |
| <span style="display:inline-block;width:16px;height:16px;background:#ced4da;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `navigator-default-element-border-color` | `#ced4da` | Navigator default element border color |
| | `navigator-default-element-border-width` | `1px` | Navigator default element border width |

---

## Selection

Multi and single selection box and handles.

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `selection-wrapper-color` | `#1971c2` | Multiple selection bounding box color |
| | `selection-wrapper-width` | `1.5px` | Multiple selection bounding box width |
| | `selection-wrapper-pattern` | `none` | Selection border dash pattern |
| | `selection-wrapper-padding` | `5` | Padding between combined bbox and selection wrapper |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `selection-frame-color` | `#1971c2` | Shape selection bounding box color |
| | `selection-frame-width` | `1.5px` | Shape selection bounding box width |
| | `selection-frame-pattern` | `none` | Shape selection border dash pattern |
| | `selection-frame-padding` | `5` | Padding between shape bbox and selection frame |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `selection-lasso-fill-color` | `#1971c2` | Selection lasso fill color |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `selection-lasso-border-color` | `#1971c2` | Selection lasso border color |
| | `selection-lasso-border-width` | `1.5px` | Selection lasso border width |
| | `selection-lasso-border-pattern` | `none` | Selection lasso border dash pattern |

---

## Snaplines

Snaplines styles

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `snaplines-horizontal-color` | `#1971c2` | Horizontal snapline color |
| | `snaplines-horizontal-width` | `1px` | Horizontal snapline stroke width |
| | `snaplines-horizontal-pattern` | `5, 5` | Horizontal snapline dash pattern |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `snaplines-vertical-color` | `#1971c2` | Vertical snapline color |
| | `snaplines-vertical-width` | `1px` | Vertical snapline stroke width |
| | `snaplines-vertical-pattern` | `5, 5` | Vertical snapline dash pattern |

---

## Halo

TBD

---

## Free Transform

Free transform handles and bounding box. Here all sizes are in HTML pixels (not scaled by the paper zoom level).

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| | `free-transform-border-padding` | `6px` | Free transform border padding |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-border-color` | `#1971c2` | Free transform bounding box color |
| | `free-transform-border-width` | `1.5px` | Free transform bounding box width |
| | `free-transform-border-pattern` | `none` | Free transform bounding box dash pattern |
| | `free-transform-handle-size` | `6px` | Free transform handle size |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-border-color` | `#1971c2` | Free transform handle border color |
| <span style="display:inline-block;width:16px;height:16px;background:#ffffff;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> |
| | `free-transform-handle-border-width` | `2px` | Free transform handle border width |
`free-transform-handle-background-color` | `#FFFFFF` | Free transform handle background color |

### State Variants

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-hover-background-color` | `#2f9e44` | Free transform handle background color when hovered |
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-hover-border-color` | `#2f9e44` | Free transform handle border color when hovered |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-active-background-color` | `#1971c2` | Free transform handle background color when active (dragged) |
| <span style="display:inline-block;width:16px;height:16px;background:#1971c2;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `free-transform-handle-active-border-color` | `#1971c2` | Free transform handle border color when active (dragged) |

## Icons

- Rotate
- Resize
- Remove
- Fork
- Connect
- Clone
- Clone and connect
- Break connections

## Interactions

| Preview | Variable | Value | Description |
|---------|----------|-------|-------------|
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `interactions-connection-candidate-highlighter-color` | `#2f9e44` | Color of candidate element highlighter when connecting |
| | `interactions-connection-candidate-highlighter-width` | `2px` | Border width of candidate element highlighter when connecting |
| | `interactions-connection-candidate-highlighter-pattern` | `none` | Border dash pattern of candidate element highlighter when connecting |
| | `interactions-connection-candidate-highlighter-padding` | `2px` | Padding of candidate element highlighter when connecting |
| <span style="display:inline-block;width:16px;height:16px;background:#2f9e44;border:1px solid #ccc;border-radius:2px;vertical-align:middle"></span> | `interactions-embedding-container-highlighter-color` | `#2f9e44` | Color of container element highlighter when embedding |
| | `interactions-embedding-container-highlighter-width` | `2px` | Border width of container element highlighter when embedding |
| | `interactions-embedding-container-highlighter-pattern` | `none` | Border dash pattern of container element highlighter when embedding |

