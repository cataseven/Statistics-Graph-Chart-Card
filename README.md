<a href="https://www.buymeacoffee.com/cataseven" target="_blank">
  <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me a Coffee" style="height: 60px !important;width: 217px !important;" >
</a>


# 📊 Home Assistant - Statistics Graph Chart Card

![Downloads](https://img.shields.io/github/downloads/cataseven/Statistics-Graph-Chart-Card/total?color=41BDF5&logo=home-assistant&label=Downloads&suffix=%20downloads&style=for-the-badge)
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/hacs/frontend)
[![GitHub Release](https://img.shields.io/github/release/cataseven/Statistics-Graph-Chart-Card.svg)](https://github.com/cataseven/Statistics-Graph-Chart-Card/releases)
[![License](https://img.shields.io/github/license/cataseven/Statistics-Graph-Chart-Card.svg)](LICENSE)
![Home Assistant](https://img.shields.io/badge/Home%20Assistant-2024.1.0%2B-blue.svg)
![Maintenance](https://img.shields.io/maintenance/yes/2026.svg)
[![GitHub Stars](https://img.shields.io/github/stars/cataseven/Statistics-Graph-Chart-Card?style=social)](https://github.com/cataseven/Statistics-Graph-Chart-Card)
[![GitHub Issues](https://img.shields.io/github/issues/cataseven/Statistics-Graph-Chart-Card?style=flat-square)](https://github.com/cataseven/Statistics-Graph-Chart-Card/issues)

An awesome feature-rich custom card for [Home Assistant](https://www.home-assistant.io/) that combines a time-series graph with live state rows — all in a single card. Built with no external dependencies, fully configurable via the visual editor or YAML.

---

## 🖼️ Preview

![image6](images/add2.gif)

![image6](images/scroll2.gif)

![image3](images/editor1.png)

![Scatter Example](images/scatter-example.png)

![Pie Example](images/pie-example.png)

![Heatmap Example](images/heatmap-example.png)

![Ranking Example](images/ranking-example.png)

![Radial Bar Example](images/radialbar-example.png)

![Calendar Example](images/calendar-example.png)

![Polar Area Example](images/polararea-example.png)

![Radar Example](images/radar-example.png)

![image6](images/duplicate.gif)

![image6](images/scroll.gif)

![image4](images/editor21.png)

![image5](images/editor3.png)

![image1](images/line.png)

![image2](images/bar.png)


---

## ✨ Features

| | |
|---|---|
| 📈 | Line, step, and bar charts with smooth Bezier curves |
| 📅 | **Built-in Date Picker** — navigate Day, Week, Month, Year views with arrow buttons, calendar popup, and preset ranges (Last 7/30 Days, Last 12 Months). Sync multiple cards with `date_picker_group` — even cards without a visible picker can follow the group. Customize visible modes with `date_picker_modes` — lock to a single mode for a minimal nav bar |
| 🪟 | **Card styling without card-mod** — set border radius, border color & width, padding, background image (with smart `/local/` path resolution), background blur (image-only — chart and header stay sharp), header color, weight, and letter-spacing directly from the editor. Combine with `rgba(...)` background colors for translucent cards over images |
| 🔢 | Live state rows with current value, MDI icons, and configurable font sizes |
| 🎯 | **Ten chart modes** — Timeline, State Timeline, Scatter, Pie (donut), Ranking (horizontal bar), Radial Bar (concentric arcs), Polar Area (variable-radius pie), Radar (spider polygon), Heatmap (days × hours), Calendar (weekly grid) — selectable from a single dropdown |
| 🎛️ | **Gauge display** — replace the state row with a half-circle gauge showing current value against min/max bounds |
| ✨ | **Sparkline mode** — ultra-compact inline graphs with no chrome, ideal for dashboard overview tiles |
| 📊 | **Rise/Fall colorization** — graph segments automatically change color as values climb or drop, with independent colors for rising, falling, and stable periods |
| ⏩ | **Trend icon** — a ▲▼⯇⯈ indicator on each state row shows the current direction of change, calculated over a configurable time window (`trend_period_hours`) |
| 🌐 | **Locale-aware formatting** — control how numbers are displayed per entity (`number_format`) and how timestamps appear card-wide (`datetime_format`), independent of your HA locale |
| 🏷️ | **Custom unit per entity** — override auto-detected units with `unit: kWh` on any entity. Essential for attributes and unitless sensors |
| 🔡 | **Axis label customization** — adjust font size and opacity of Y-axis and X-axis labels independently for a clean, tailored look |
| 📌 | **Axis tick marks** — optional small tick lines at each label position, controllable independently for X and Y axes |
| 🕐 | **Dynamic Graph Hours** — filter data to specific hours each day with `graph_start_hour` and `graph_end_hour`. Accepts fixed numbers or sensor entities (e.g. `sensor.sunrise_hour`) for sunrise-to-sunset views that adapt throughout the year |
| 🛠️ | **Full visual editor** — every option is configurable through the Lovelace UI without touching YAML; entities can be reordered by drag-and-drop. The editor adapts dynamically: irrelevant options hide based on the selected chart mode |
| ↕️ | Dual Y-axis support (primary + secondary) with per-axis bounds and configurable tick count |
| ↕️ | **Independent Y2 axis toggle** — show or hide the secondary (right) Y axis labels without affecting the primary axis |
| ↕️ | **Independent Y-axis** — `y_axis: independent` gives each entity its own hidden scale based on its min/max, enabling trend comparison across sensors with wildly different units (°C, %, lux, hPa) on a single graph |
| 🎨 | Color thresholds with **direction** (vertical gradient or horizontal per-segment) and **transition** (smooth blend or hard switch) |
| 🔺 | Min / Max extrema labels — always on, on click, or never |
| ➖ | Average line — dashed reference at the mean value for the visible window |
| 💬 | Tooltip with crosshair on hover |
| 🌅 | Per-entity gradient fill with same-hue fade — applies to both area charts and bar charts (with rounded corners) |
| ▦ | Grid lines — horizontal + vertical aligned to actual data points |
| 📉 | Logarithmic scale |
| 🔍 | **Zoom brush** — click and drag on the graph to zoom into a time range; double-click or "Reset zoom" to restore |
| 📌 | **Annotations** — add threshold lines, event markers, time span highlights, and comfort zone bands to the graph. Entity-driven or manual timestamps, with per-annotation opacity and Jinja2 template support |
| 🔄 | **Tooltip sync** — hover one card and see crosshairs on all synced cards, with optional named groups |
| 📊 | **Stacked** mode — stack line/area/bar entities to show composition |
| ↔️ | **Time Offset** — per-entity hour offset to overlay the same sensor from different periods on one graph. Supports helper entities (e.g. `input_number`) for dynamic offset values |
| 〰️ | Soft bounds (`~` prefix) — axis expands when data exceeds the bound |
| 🔣 | `state_map` for non-numeric entities (binary sensors, input selects) |
| 🔗 | Attribute reading with dot-notation nested path support |
| ⏩ | Forward-fill for sparse sensors (e.g. weather entities) |
| 🎨 | Adaptive state color — state row inherits entity line color automatically |
| 🎚️ | **Interval picker** — quick-select time range buttons (1H–1Y) directly on the card, no editor needed |
| ⚡ | **Auto scale points** — automatically reduces data density for longer time ranges, keeping performance smooth |
| 🔀 | **Attribute switcher** — per-entity dropdown on the card to switch between state and any numeric attribute on the fly |
| 🔍 | **Scrollable graph** — set a visible window smaller than the data range and scroll horizontally through history |
| ↔️ | **Configurable icon position** — place the header icon on the left or right side of the title |
| 🏷️ | **Compact Legend** — color-coded entity name key below the graph with configurable position (left, center, right). Click any legend item to temporarily hide that entity from the graph |
| 📊 | **Per-entity legend stats** — choose any combination of Min, Avg, Max, Last for each entity's legend row. Click to toggle entity visibility |
| 🏷️ | **Vertical axis labels** — optional vertical unit labels on the left and right edges of the graph. Defaults to the entity's unit of measurement, with custom text override |
| 🕐 | **Smart X-axis labels** — when the time range spans multiple days, midnight ticks automatically show the date (e.g. "28 Mar") while other ticks show `HH:mm`. Tick density adapts to label width and font size |
| ⬇️ | **Bottom state rows** — place entity state rows below the graph instead of above with `bottom-left`, `bottom-center`, `bottom-right` alignment |
| 📏 | **Grid aligned to tick marks** — horizontal grid lines match Y axis tick values exactly |
| 🔀 | **Value Transform** — apply a JavaScript expression to every data point using `x`, `first`, `min`, `max`, `avg`, `last`, `index` — ideal for normalize-to-zero, splitting sensors, and percentage calculations |
| 📏 | **Range Band** — per-entity min/max shaded band behind the line showing value fluctuation within each data bucket |
| 🕳️ | **Break on Gaps** — per-entity toggle to break the line at long `unavailable` / `unknown` outages instead of carrying the last known value across the gap |
| ↔️ | **Dynamic Y-axis width** — axis label areas auto-expand to fit longer numbers without clipping |
| ⚡ | **Energy Date Sync** — sync the card's time range with HA's Energy dashboard date picker or [energy-period-selector-plus](https://github.com/flixlix/energy-period-selector-plus) |
| 🔌 | **External Statistics** — display imported statistics that have no regular entity (e.g. `gazpar:gazpar_consumption`) by setting `statistic_id` |
| 📅 | **Long-range views** — `group_by: week` and `month` with native HA statistics periods, `graph_start` anchoring to calendar boundaries, and smart X-axis labels that adapt to the grouping mode |
| ⚡ | **Change aggregation** — `aggregate_func: change` uses HA's native `change` field for energy, gas, and water meters. Combine with `group_by: date/week/month` for accurate consumption charts |
| 🔀 | **Stacked Groups** — per-entity `stack_group` names let you create multiple side-by-side stacked bar groups on a single chart |
| 🏷️ | **Template names** — use `{{ state_attr('sensor.x', 'attr') }}` with Jinja2 filters (`capitalize`, `upper`, `replace()`, `round()`, etc.) for dynamic entity names |
| ↔️ | **Horizontal state layout** — `state_layout: horizontal` flows entity values side by side instead of stacking vertically |
| 🔢 | **Y-axis decimals** — card-level `y_axis_decimals` overrides per-entity decimals for axis labels only, keeping state row precision separate |
| ⏱️ | **X-axis interval** — `x_axis_interval` for manual tick spacing (1h–3M) with clean boundary snapping |
| 📅 | **Show Full Period** — extend the X-axis to cover a complete calendar period (day, week, month, year) with a "now" indicator line, leaving empty space after the current time. Ideal for imported data or comparing today vs yesterday |
| 🔋 | **Battery icon** — `battery_entity` displays a color-coded battery level indicator in the header or state row, with configurable low threshold |
| 📡 | **Attribute Data Source** — read chart data from an entity attribute array (forecast, spot prices) instead of history. Supports future timestamps for EPEX, Nordpool, Tibber, solar forecasts, and weather predictions. Also accepts numeric/categorical time fields (`month_of_year`, `day_of_year`, `hour_of_day`, epoch seconds/ms) so monthly summaries and hourly profiles work without artificial timestamps |
| 📅 | **Group by Year** — `group_by: year` for multi-year trend views with automatic bar width and X-axis labels |
| 🔄 | **Invert bars** — per-entity `invert: true` draws bars downward from zero. Combine with `stacked: true` for butterfly charts (energy import/export, network in/out) |
| 🔁 | **Rolling date picker window** — `date_picker_step` turns the picker into an N-unit rolling window. `step: 4` + `mode: week` shows the last 4 weeks and prev/next jumps a full 4 weeks at a time |
| 💾 | **Long-term statistics auto-routing** — entities with `state_class` declared automatically use HA's long-term statistics for ranges beyond recorder retention. Set `statistic_id` explicitly or use `hours_to_show > 240` to opt in for short ranges. A console warning lists entities lacking `state_class` when the range exceeds retention |
| 📈 | **Static data carry-forward** — when a sensor stops emitting state changes, the last known value is carried forward to "now" instead of leaving the chart blank. Matches the behavior of HA's built-in statistics card |
| ⚠️ | **Offline sensor gaps** — when HA reports a sensor as `unavailable`, the line breaks at that point and resumes when the sensor recovers. Makes it instantly obvious when a sensor was offline versus when its value was simply steady |
| 🥧 | **Pie chart styles** — `pie_style` presets (Classic, Thick, Donut, Thin) with optional `pie_3d` depth effect, `pie_spacing` for gaps between slices, and automatic rounded slice corners. Slice labels show the actual value with unit. Customize slice and center label fonts/colors with `pie_label_font_size`, `pie_label_color`, `pie_center_font_size`, and `pie_center_color` — all accept theme variables |
| 🎯 | **Snap-to-data tooltips** — hovering over a line graph snaps the tooltip and dot to the nearest real data point instead of interpolating fake values between samples. The crosshair line aligns with the snapped point too, so what you see is exactly what your sensor recorded |
| 🔤 | **Theme-aware fonts** — every canvas-rendered chart (Pie, Heatmap, Calendar, Ranking, Radial Bar, Polar Area, Radar, Gauge, axis labels) uses your active HA font (`--primary-font-family`) instead of generic sans-serif |
| 🧹 | **Clean YAML output** — the visual editor only writes fields you've actually customized. New cards start with 5 lines, not 80. Toggle a setting and it appears in YAML; revert to default and it disappears. Explicit overrides are always preserved |
| 🏷️ | **Y-axis state names** — when graphing entities with `state_map` (washing machines, alarm panels, media players), the Y-axis automatically shows the original state names (`idle`, `running`, `done`) instead of `0`, `1`, `2`. Optional friendly labels supported via `value, label` in the editor |
| 🎨 | **Custom axis colors** — `y_axis_color`, `x_axis_color`, and `x_axis_date_color` let you color-match the axis labels and tick marks to your dashboard theme |
| ✨ | **Bar hover highlight** — bars brighten on mouse hover so it's obvious which bar a tooltip refers to, especially in stacked or multi-entity charts. On mobile, the highlight persists while the finger is held down via a JS-managed class (CSS `:hover` is unreliable on touch devices) |
| 🎨 | **Color templates** — all color fields (`color`, `icon_color`, `state_color`, `point_colors`, axis/grid colors) accept Jinja2 `{{ }}` templates evaluated server-side by HA via `render_template` WebSocket subscriptions. Use a central `sensor.entity_colors` to manage all entity colors from one place. In the editor, the color picker automatically dims when a template is detected |
| 📅 | **`graph_start: tomorrow`** — sets the graph window to tomorrow 00:00 → end of day, perfect for displaying next-day spot prices (Nord Pool, EPEX, Tibber) via `data_attribute`. The window extends into the future automatically without requiring `show_full_period` |
| 📏 | **Grid customization** — per-axis control over grid line appearance: `y_grid_style` / `x_grid_style` (dashed, solid, dotted, long-dash), `y_grid_width` / `x_grid_width` (thickness in px), `y_grid_color` / `x_grid_color` (any CSS color or template), and `y_grid_opacity` / `x_grid_opacity` to dial the grid up or down without retyping rgba colors. All configurable from the editor's Y Axis and X Axis tabs |
| 📱 | **Mobile touch improvements** — tooltip appears instantly on first tap (no finger movement needed). Long-press (600ms) + drag activates brush zoom; a quick slide shows the tooltip. Bar highlights persist while the finger is held down |
| 🥧 | **Pie/Radial decimals** — entity `decimals` setting now controls the precision of percentage labels in slice labels, tooltips, and radial bar overlays — not just the value display |
| 🔮 | **Forecast Horizon** — per-entity `forecast_horizon: N` shifts each recorded data point along the X-axis. **Positive values** (e.g. `1`) shift forward — for sensors whose current state predicts T+N hours ahead (e.g. Solcast PV forecast in 1 hour); the X-axis is extended automatically to keep the shifted line visible. **Negative values** (e.g. `-24`) shift backward — useful with attribute-based forecasts to overlay tomorrow's data onto today's chart. Independent from `offset` — both can be combined |
| ⏱️ | **Now Line** — a vertical marker showing the current moment, enabled by default. Customize `now_line_color`, `now_line_opacity`, `now_line_width`, and `now_line_style` (solid, dashed, dotted, long-dash) or disable with `show_now_line: false` |
| 📐 | **Round Y-axis ticks** — the Y axis picks clean round numbers (0, 500, 1000, 1500) that fit within your data range without expanding it. Enabled by default; disable with `y_axis_round_ticks: false` |
| 🎯 | **Primary Value dropdown** — `primary_state_as` controls what the big value in the state row shows: live state (default), last aggregated point, or Sum / Avg / Min / Max / First over the visible window. Ideal for clean header-only entities |
| 📊 | **Show Range** — `show_range_values: true` displays the visible window's min and max as a subdued `(min → max)` suffix next to the primary value. Perfect for compact "records" cards (`show_graph: false` + `primary_state_as: min`/`max`) where the range previously was only reachable via the graph tooltip |
| 📑 | **Stacked name layout** — `name_position: below` places the entity name centered below the primary value (ApexCharts-style), great for mobile and header-only entities |
| 🎨 | **Card shadow & border toggles** — `card_shadow: false` and `card_border: false` allow a flat borderless look or blending with decorated backgrounds |

---

## 📑 Table of Contents

| Section | Description |
|---|---|
| [Installation](#-installation) | HACS and manual setup |
| [Quick Start](#-quick-start) | Minimal YAML to get started |
| [Configuration](#%EF%B8%8F-configuration) | Card-level and entity-level options |
| [Chart Modes](#-chart-modes) | Timeline, Scatter, Pie, Ranking, Heatmap, Calendar, Radial Bar, Polar Area, Radar |
| [Feature Guides](#-feature-guides) | Date Picker, Energy Sync, Zoom, Sparkline, Annotations, and more |
| [Examples](#-examples) | Ready-to-use YAML configurations |
| [Reference](#-reference) | Aggregation functions, date formats, bounds, tap actions |
| [Visual Editor](#%EF%B8%8F-visual-editor) | Editor tabs, drag-and-drop, dynamic behavior |

---

## 📦 Installation

### HACS (recommended)

1. Open **HACS
2. Search from the search bar: Statistics Graph Chart Card
3. Install **Home Assistant - Statistics Graph Chart Card**
4. Hard-refresh your browser

### Manual

1. Download `Home Assistant - Statistics Graph Chart Card.js` from the [latest release](../../releases/latest)
2. Copy it to `/config/www/`
3. Add the resource in **Settings → Dashboards → Resources**:

```yaml
url: /local/Home Assistant - Statistics Graph Chart Card.js
type: module
```

---

## 🚀 Quick Start

```yaml
type: custom:statistics-graph-chart-card
card_header: Living Room
entities:
  - entity: sensor.temperature_living
    name: Temperature
    color: "#ff6b35"
```

> **No YAML needed?** The card has a full visual editor built in. Click the pencil icon on any card in the Lovelace UI to configure everything — including rise/fall colors, trend settings, and number formats — without writing a single line of YAML. See [Visual Editor](#️-visual-editor) for details.

---

## ⚙️ Configuration

<details>
<summary>Show card-level and entity-level option tables</summary>

### 🃏 Card Options

These options apply to the whole card.

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `chart_mode` | string | `"timeline"` | Chart visualization mode. See [Chart Modes](#-chart-modes). `timeline` \| `scatter` \| `pie` \| `ranking` \| `radialbar` \| `polararea` \| `radar` \| `heatmap` \| `calendar` |
| `sparkline` | boolean | `false` | Compact mode — strips all chrome (header, axes, grid, toolbar) and renders tiny inline graphs. See [Sparkline Mode](#-sparkline-mode). Only available in Timeline mode. |
| `card_header` | string | `""` | Title shown at the top. Leave empty to hide. |
| `card_icon` | string | `null` | MDI icon next to the title, e.g. `mdi:thermometer` |
| `card_icon_image` | string | `null` | URL to a custom image. Overrides `card_icon`. |
| `card_icon_color` | string | `null` | Color of the header icon (CSS color). Set to `"threshold"` to color dynamically based on the first entity's value and its color threshold rules. |
| `card_header_size` | string | `null` | Font size of the title and battery icon. The battery indicator scales proportionally with this value. Accepts CSS values like `16px` or `1.2em`. |
| `card_icon_size` | string | `null` | Size of the header icon, e.g. `22px` |
| `card_icon_position` | string | `"left"` | Header icon position: `left` or `right` |
| `card_shadow` | boolean | `true` | Show the default HA card drop shadow. Disable for a flat look or when the card sits on a decorated background. |
| `card_border` | boolean | `true` | Show the default HA card border. Disable for a cleaner borderless appearance. |
| `battery_entity` | string | `null` | Entity ID reporting battery level (0–100%). Shows a color-coded battery icon with percentage in the header (when header exists) or state row (when no header). See [Battery Icon](#-battery-icon). |
| `battery_low_threshold` | string/number | `20` | Battery percentage below which the icon turns red. Accepts a number, entity ID (`sensor.x`), or entity attribute (`sensor.x.attribute`). |
| `align_header` | string | `"default"` | Header alignment: `default` / `left` / `center` / `right` |
| `state_layout` | string | `"default"` | State row layout: `default` (vertical stack) / `horizontal` / `horizontal-center` / `horizontal-right`. Horizontal modes flow entities side by side in a single row. |
| `chart_align` | string | `"center"` | Horizontal alignment for the non-scrolling chart modes. `center` (default) keeps the chart centered in the card. `left` pins it to the left edge — for Ranking, the name-label strip shrinks so bars start closer to the left. `right` mirrors the layout to the right edge — for Ranking, bars grow from right to left with name labels on the right. Applies to Pie, Radial Bar, Polar Area, Radar, and Ranking modes. |
| `hours_to_show` | number | `24` | Hours of history to load and display. Ignored when `graph_start` is set to `week`, `month`, or `year` — the calendar period defines the range instead. |
| `points_per_hour` | number | `2` | Data points fetched per hour (global default). Integer only. |
| `auto_scale_points` | boolean | `false` | Automatically pick bucket size and `group_by` based on the visible time window. Falls back to the configured values when any entity uses `offset`, `forecast_horizon`, or `data_attribute`. See [Auto Scale Points](#-auto-scale-points). |
| `height` | number | `150` | Graph area height in pixels |
| `group_by` | string | `"interval"` | Bucketing strategy: `interval` / `hour` / `date` / `week` / `month` / `year`. When set to `week`, `month`, or `year`, data is fetched using native HA statistics periods for accuracy and performance. See [Long-Range Views](#-long-range-views). |
| `update_interval` | number | `null` | Auto-refresh interval in seconds. Empty = HA events only. |
| `bar_spacing` | number | `4` | Gap between bar columns in pixels. Timeline mode only. |
| `stacked` | boolean | `false` | Stack entities on top of each other. Timeline mode only. See [Stacked Mode](#-stacked-mode). |
| `min_bound_range` | number | `null` | Minimum span of the primary Y axis |
| `min_bound_range_secondary` | number | `null` | Minimum span of the secondary Y axis |
| `lower_bound` | string/number | `null` | Hard or soft minimum for the primary Y axis. See [Bounds](#-bounds). |
| `upper_bound` | string/number | `null` | Hard or soft maximum for the primary Y axis. See [Bounds](#-bounds). |
| `lower_bound_secondary` | string/number | `null` | Hard or soft minimum for the secondary Y axis. See [Bounds](#-bounds). |
| `upper_bound_secondary` | string/number | `null` | Hard or soft maximum for the secondary Y axis. See [Bounds](#-bounds). |
| `y_axis_ticks` | number | `4` | Number of tick marks (grid lines + labels) on the Y axis. |
| `y_axis_decimals` | number | `null` | Number of decimal places for Y-axis labels. Overrides per-entity `decimals` for axis labels only — state row values are not affected. Leave empty for auto. |
| `y_axis_round_ticks` | boolean | `true` | Snap Y-axis tick values to clean round numbers (e.g. 0, 500, 1000, 1500) that fit within the data range without expanding it. Produces tidy, evenly-spaced labels similar to Excel's default. Disable to let tick values follow the exact data range. |
| `show_y_axis_label` | boolean | `false` | Show vertical unit labels on the left and/or right edge of the graph. When enabled, defaults to the unit of measurement of the first entity on each axis. |
| `y_axis_label` | string | `null` | Custom text for the left (primary) vertical axis label. Overrides the auto-detected unit. Requires `show_y_axis_label: true`. |
| `y2_axis_label` | string | `null` | Custom text for the right (secondary) vertical axis label. Overrides the auto-detected unit. Requires `show_y_axis_label: true`. |
| `y_axis_font_size` | number | `null` | Font size of Y-axis numeric labels in pixels. Default is 10. |
| `y_axis_font_opacity` | number | `null` | Opacity of Y-axis labels. 0 = invisible, 1 = fully opaque. Default is 0.65. |
| `y_axis_color` | string | `null` | Custom color for Y-axis labels and tick marks. Accepts any CSS color (hex, rgba, color name) or a CSS variable like `var(--my-color)`. Leave empty for theme default. |
| `x_axis_font_size` | number | `null` | Font size of X-axis time labels in pixels. Default is 10. |
| `x_axis_font_opacity` | number | `null` | Opacity of X-axis labels. 0 = invisible, 1 = fully opaque. Default is 0.5. |
| `x_axis_color` | string | `null` | Custom color for X-axis time labels and tick marks. Accepts any CSS color or CSS variable. Leave empty for theme default. |
| `x_axis_date_color` | string | `null` | Custom color for X-axis date markers (the bold date dividers shown in 12+ hour views). Defaults to `--primary-color` so dates stand out. Set to match `x_axis_color` for a uniform axis. |
| `pie_style` | string | `"donut"` | Pie chart visual preset: `classic` (full pie), `thick` (wide donut), `donut` (default), or `thin` (narrow ring). Pie mode only. |
| `pie_spacing` | number | `0` | Gap between pie slices in degrees (0–15). Spaced slices automatically get rounded corners. Pie mode only, donut styles only. |
| `pie_3d` | boolean | `false` | Adds depth and a perspective effect to the pie chart with subtle shadows and a glossy highlight on top. Works with any `pie_style`. Pie mode only. |
| `pie_label_font_size` | number | `null` | Font size in pixels of slice value labels (the per-slice numbers like *"21.1 kWh"*). Leave empty for auto-size based on chart radius. Pie mode only. |
| `pie_label_color` | string | `null` | Color for slice value labels. Accepts any CSS color (hex, rgba, name) or CSS variable like `var(--accent-color)`. Leave empty for auto white (high contrast against any slice color). Pie mode only. |
| `pie_label_format` | string | `"value"` | What to show inside each pie slice: `value` (number with unit, e.g. *"42.0 kWh"*), `percentage` (share of the total, e.g. *"23%"*), or `both` (value followed by percentage). Precision is controlled by the entity's `decimals` setting — affects both value and percentage display. Pie mode only. |
| `pie_center_font_size` | number | `null` | Font size in pixels of the center total value shown in the donut hole. Requires `show_tooltip_total: true`. Leave empty for auto-size. Pie mode only. |
| `pie_center_color` | string | `null` | Color of the center total value and its sub-label (which inherits the same color with reduced opacity). Accepts any CSS color or variable. Leave empty for the theme default. Pie mode only. |
| `x_axis_interval` | string | `null` | Manual X-axis tick spacing. Values: `1h`–`12h`, `1d`, `2d`, `7d`, `1w`, `2w`, `1M`, `3M`. Ticks snap to clean boundaries (hour starts, midnight, Mondays, 1st of month). Leave empty for auto. |
| `datetime_format` | string | `"system"` | Controls how timestamps appear on the X-axis, tooltips, and extrema labels. See [Date Formats](#-date-formats). |
| `show_grid` | boolean | `true` | Show grid lines. Available in Timeline and Scatter modes. |
| `y_grid_style` | string | `"dashed"` | Line pattern for horizontal (Y-axis) grid lines: `dashed`, `solid`, `dotted`, or `long-dash`. Also accepts a custom SVG stroke-dasharray like `6 2 2 2`. |
| `y_grid_width` | number | `1` | Thickness of horizontal grid lines in pixels. Accepts decimals like `0.5`. |
| `y_grid_color` | string | `null` | Color of horizontal grid lines. Accepts any CSS color, variable, or `{{ }}` template. Leave empty for theme default. |
| `y_grid_opacity` | number | `0.15` | Opacity of horizontal grid lines, from `0` (invisible) to `1` (fully opaque). Lower values keep the grid subtle without competing with the data. |
| `x_grid_style` | string | `"dashed"` | Line pattern for vertical (X-axis) grid lines: `dashed`, `solid`, `dotted`, or `long-dash`. |
| `x_grid_width` | number | `1` | Thickness of vertical grid lines in pixels. |
| `x_grid_color` | string | `null` | Color of vertical grid lines. Accepts any CSS color, variable, or `{{ }}` template. |
| `x_grid_opacity` | number | `0.15` | Opacity of vertical grid lines, from `0` (invisible) to `1` (fully opaque). |
| `show_tooltip` | boolean | `true` | Show hover tooltip with crosshair |
| `show_tooltip_total` | boolean | `true` | Controls total/summary displays across chart modes. Timeline/Scatter: Total row in tooltip. Pie/Polar Area: total in donut center (off = full pie). Radial Bar: average in center. Ranking: percentage labels on bars and Share row in tooltip. |
| `show_y_axis` | boolean | `true` | Show primary (left) Y axis value labels. Available in Timeline and Scatter modes. |
| `show_y2_axis` | boolean | `true` | Show secondary (right) Y axis value labels independently. Only visible when at least one entity uses `y_axis: secondary`. Disable to hide right-side labels while keeping secondary entities plotted. |
| `show_x_axis` | boolean | `true` | Show X axis labels (time in Timeline, values in Scatter). Available in Timeline and Scatter modes. |
| `show_x_ticks` | boolean | `false` | Draw small tick marks at each X-axis label position. |
| `show_y_ticks` | boolean | `false` | Draw small tick marks at each Y-axis label position. |
| `graph_start_hour` | number / entity | `null` | Daily start hour filter. Points before this hour each day are hidden, creating natural line breaks between days. Accepts a fixed number (`6` = 06:00, `6.5` = 06:30) or a sensor entity ID (`sensor.sunrise_hour`) for dynamic values. Works with Date Picker: in Day mode trims the X-axis, in Week/Month/Year modes filters per day. See [Dynamic Graph Hours](#-dynamic-graph-hours). |
| `graph_end_hour` | number / entity | `null` | Daily end hour filter. Points after this hour each day are hidden. Same format as `graph_start_hour`. Use with `sensor.sunset_hour` for sunrise-to-sunset views. |
| `graph_start` | string | `null` | Snaps the graph start to a calendar boundary: `tomorrow` (tomorrow 00:00 — ideal for next-day spot prices via `data_attribute`), `week` (Monday 00:00), `month` (1st of month), `year` (Jan 1st). When set to `tomorrow`, the window automatically extends to cover the full next day even without `show_full_period`. Ignored when the interval picker is active. See [Long-Range Views](#-long-range-views). |
| `show_full_period` | boolean | `false` | Extends the X-axis to cover the full calendar period instead of stopping at "now". A dashed vertical line marks the current time. Works with `graph_start` (week/month/year) and `energy_date_sync`. Not required for `graph_start: tomorrow` — that extends automatically. See [Show Full Period](#-show-full-period). |
| `card_background_color` | color | `null` | Custom background color for the card. Accepts any CSS color (hex, rgba, name). Use `rgba(R, G, B, A)` for translucent cards. Replaces `card_mod` workarounds — this value persists across re-renders. |
| `card_padding` | string/number | `null` | Inner spacing of the card. Accepts a single number (treated as px) or any CSS shorthand like `8px 16px` or `0`. Leave empty for theme default. |
| `card_border_radius` | string/number | `null` | Roundness of the card corners. Accepts a number (px) or any CSS value like `12px`, `1rem`, `0`. Leave empty for theme default. |
| `card_border_color` | color | `null` | Custom color for the card border. Only effective when `card_border` is `true`. Accepts any CSS color or variable. |
| `card_border_width` | string/number | `null` | Border thickness. Accepts a number (px) or any CSS value like `2px`. Only effective when `card_border` is `true`. |
| `card_background_image` | string | `null` | URL of an image to use as the card background. Local files in `/config/www/` resolve via friendly paths — `local/photos/sunset.jpg`, `photos/sunset.jpg`, and `/local/photos/sunset.jpg` all work, as do external URLs (`https://...`). The image overlays the background color (use `rgba(...)` colors for translucent overlays that show the image through). |
| `card_background_blur` | number | `null` | Blur amount in pixels applied to `card_background_image` only. The chart, header, and other content stay sharp. `0` or empty = no blur. Useful for soft, atmospheric backgrounds (try `4`–`12`). |
| `card_header_color` | color | `null` | Custom color for the header title text. Accepts any CSS color or variable. Leave empty for theme default. |
| `card_header_weight` | string/number | `null` | Header text font weight. Accepts CSS keywords (`light`, `normal`, `bold`) or numbers (`300`, `400`, `600`, `700`). Leave empty for theme default. |
| `card_header_letter_spacing` | string/number | `null` | Header letter spacing. Accepts a number (treated as px) or any CSS value like `0.5px`, `normal`, `-0.02em`. Leave empty for theme default. |
| `show_legend` | boolean | `false` | Show a compact color-coded entity name key below the graph. Click any item to temporarily toggle that entity's visibility on the graph. For per-entity stats, use the entity-level Legend toggle. |
| `legend_position` | string | `"center"` | Position of the compact legend: `left` / `center` / `right`. The legend flows inline at the chosen alignment. |
| `logarithmic` | boolean | `false` | Logarithmic Y axis scale. Timeline mode only. |
| `animate_graph` | boolean | `false` | Draw-in animation on load (Timeline mode). Also enables a slice-grow animation on every data refresh for Pie, Radial Bar, and Polar Area modes — slices sweep out from zero whenever the underlying values change. |
| `max_visible_interval` | number | `null` | Maximum visible time range in hours. Enables horizontal scrolling. Works in Timeline and State Timeline modes. |
| `scroll_mode` | string | `"scrollbar"` | How the scroll works when `max_visible_interval` is active. `scrollbar` (default) shows a bottom scrollbar; `wheel` hides it and lets the mouse wheel scroll horizontally. |
| `state_timeline_corner_radius` | number | `3` | Roundness of state_timeline segment corners, in pixels. `0` = sharp edges. Larger values produce rounder / pill-shaped segments (capped at half the row height). State Timeline mode only. Advanced users can also target the `sgc-stl-cell` CSS class from `card_mod` for per-state styling. |
| `show_interval_picker` | boolean | `false` | Show quick-select time range buttons on the card. Default set: 1H, 2H, 4H, 8H, 12H, 24H, 7D. Customize with `interval_options`. |
| `interval_picker_position` | string | `"left"` | Position of the interval picker: `left` / `center` / `right` |
| `interval_options` | list | `null` | Which interval buttons to show. Example: `["2H", "12H", "24H", "7D"]`. When not set, the default compact set (1H–24H + 7D) is used. Available labels: `1H`, `2H`, `4H`, `8H`, `12H`, `24H`, `3D`, `7D`, `14D`, `30D`, `90D`, `6M`, `1Y`. |
| `show_attribute_list` | boolean | `false` | Show per-entity attribute dropdown selectors on the card |
| `attribute_list_position` | string | `"left"` | Position of the attribute list: `left` / `center` / `right` |
| `tooltip_sync` | boolean | `false` | Broadcast hovered timestamp to other synced cards. Timeline mode only. |
| `tooltip_sync_group` | string | `null` | Named group for tooltip sync. Cards with the same name sync only with each other. Leave empty to sync with all. |
| `energy_date_sync` | boolean | `false` | Sync the card's time range with HA's Energy dashboard date picker or the [energy-period-selector-plus](https://github.com/flixlix/energy-period-selector-plus) custom card. When the user selects a date range, this card automatically updates to show the same period. See [Energy Date Sync](#-energy-date-sync). |
| `show_date_picker` | boolean | `false` | Show a built-in date navigation bar with Day/Week/Month/Year buttons, arrow navigation, calendar popup, and preset ranges. Cannot be used together with `energy_date_sync`. See [Date Picker](#-date-picker). |
| `date_picker_position` | string | `top` | Position of the date picker bar. `top` or `bottom`. |
| `date_picker_group` | string | `null` | Named group for date picker sync. Cards with the same group name share date selection — change the date on one card and all cards in the group update together. Works even on cards without `show_date_picker` — a single card with a visible picker can control all other cards in the group. |
| `date_picker_modes` | list | `null` | Which period buttons to show: `day`, `week`, `month`, `year`. Example: `[month, year]`. When only one mode is listed, the D/W/M/Y buttons are hidden and the navigation is centered. Default (null) = all four modes visible. |
| `date_picker_default_mode` | string | `null` | Forces the date picker to always open in a specific mode regardless of the last-used state. Values: `day`, `week`, `month`, `year`. Leave empty (default) for *Auto* — the picker remembers the last mode you selected. Useful on shared dashboards where you always want the picker to start on, say, Month view. |
| `date_picker_step` | number | `1` | Window width in units of the selected mode. `1` = single-unit window (legacy behavior — one day, one month, etc.). `>1` turns the picker into a rolling N-unit window: prev/next buttons jump a full N units at a time. Example: `4` with `week` mode shows the last 4 weeks and navigates back/forward 4 weeks per click. See [Date Picker → Window Step](#-date-picker). |
| `annotations` | list | `[]` | Reference lines and markers on the graph. Timeline mode only. See [Annotations](#-annotations). |
| `show_now_line` | boolean | `true` | Show a vertical line marking the current moment on the graph. Timeline mode only. |
| `now_line_color` | string | `null` | Color of the now line. Accepts any CSS color or variable. Leave empty for theme default. |
| `now_line_opacity` | number | `null` | Opacity of the now line (0–1). Leave empty for default. |
| `now_line_width` | number | `null` | Thickness of the now line in pixels. Leave empty for default. |
| `now_line_style` | string | `null` | Line pattern for the now line: `solid`, `dashed`, `dotted`, or `long-dash`. Leave empty for default. |

---

### 🔷 Entity Options

Each entry under `entities` supports the following options.

#### 📋 General

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `entity` | string | **required** | HA entity ID. Can be left empty when using `statistic_id`. |
| `statistic_id` | string | `null` | For imported/external statistics that have no regular entity (e.g. `gazpar:gazpar_consumption`). These exist only in the statistics database. Leave empty for normal entities. See [External Statistics](#-external-statistics). |
| `name` | string | `null` | Custom display name. Leave empty to hide the name entirely — only shown when explicitly set. Supports HA-style templates: `{{ states('sensor.x') }}`, `{{ state_attr('sensor.x', 'attr') }}` with Jinja2 filters like `capitalize`, `upper`, `replace()`. See [Template Names](#-template-names). |
| `unit` | string | `null` | Custom unit label (e.g. `kWh`, `°C`, `%`). Overrides the auto-detected `unit_of_measurement`. Useful for attributes, unitless sensors, or when you want a different label. Appears in state row, tooltip, chart center, and axis labels. |
| `y_axis` | string | `"primary"` | `primary` (left), `secondary` (right), or `independent` (hidden, own scale). Independent entities are scaled to their own min/max — ideal for overlaying sensors with different units for trend comparison. See [Independent Y-Axis](#-independent-y-axis). |
| `aggregate_func` | string | `"avg"` | Aggregation: `avg` / `min` / `max` / `last` / `first` / `median` / `sum` / `change` / `delta` / `diff`. The `change` option uses HA's native statistics `change` field — ideal for energy, gas, and water meters with `group_by: date/week/month`. |
| `decimals` | number | `1` | Decimal places shown in state row and labels |
| `attribute` | string | `null` | Read an attribute instead of state. Supports dot notation: `forecast.0.temperature` |
| `value_factor` | number | `0` | Multiplies value by 10^N. `-3` = ÷1000, `2` = ×100 |
| `value_transform` | string | `null` | JavaScript expression to transform each data value. Available variables: `x` (current value), `first`, `last`, `min`, `max`, `avg` (series stats), `index` (point position). Applied after `value_factor`. Example: `return x - first`. See [Value Transform](#-value-transform). |
| `data_attribute` | string | `null` | Read chart data from an entity attribute array instead of history. The attribute must contain an array of objects with time and value fields. Ideal for forecast/price data (EPEX, Nordpool, weather). See [Attribute Data Source](#-attribute-data-source). |
| `data_time_field` | string | `"start_time"` | Name of the time field in each array item when using `data_attribute`. |
| `data_value_field` | string | `"price_per_kwh"` | Name of the value field in each array item when using `data_attribute`. |
| `data_time_unit` | string | `"iso"` | How to interpret the time field. `iso` = string or epoch ms (default — existing behavior). `epoch_seconds` / `epoch_ms` = Unix timestamp. `month_of_year` (1–12), `day_of_year` (1–366), `week_of_year` (1–53), `hour_of_day` (0–23) = numeric category — perfect for monthly summaries, day-of-year datasets, and hourly profiles without generating artificial timestamps. See [Attribute Data Source → Time Unit](#-attribute-data-source). |
| `data_time_year` | number | `null` | Reference year used to anchor categorical time units (`month_of_year`, `day_of_year`, `week_of_year`). Empty = current year. Has no effect for `iso` or `epoch_*` units. |
| `offset` | string/number | `0` | Shifts this entity backward in time by the given number of hours. Use to overlay the same sensor from different periods. `24` = yesterday, `168` = last week, `720` = last month. Also accepts a helper entity ID (e.g. `input_number.my_offset`) for dynamic offset — the entity's state is read as hours. See [Time Offset](#-time-offset). |
| `forecast_horizon` | number | `null` | For forecast sensors whose current state predicts T+N hours ahead (e.g. "Solar forecast in 1 hour"). Shifts each recorded data point forward by N hours so the value lands at its target future time on the X axis. The X axis is extended automatically to keep the shifted points visible. Independent from `offset` — both can be combined. See [Forecast Horizon](#-forecast-horizon). |
| `points_per_hour` | number | `null` | Per-entity override. Inherits card-level setting if empty. |
| `number_format` | string | `"system"` | Controls how numbers are displayed in the state row and tooltip. `system` follows HA's locale; `comma` forces European style (1.234,56); `dot` forces English style (1,234.56). Useful when mixing sensors from different regional sources. |
| `datetime_format` | string | `"system"` | **Deprecated** — use the card-level `datetime_format` instead. Entity-level values still work for backward compatibility and override the card setting when present. |
| `fixed_value` | boolean | `false` | Draw a flat horizontal reference line at the current value instead of history |
| `invert` | boolean | `false` | Draws bars downward from the zero line. Tooltip, state row, and extrema labels show positive values. Use with `stacked: true` for butterfly charts. See [Invert Bars](#-invert-bars-butterfly-charts). |
| `state_map` | list | `null` | Map non-numeric states to numbers for graphing. See [State Map](#-state-map). |
| `tap_action` | object | `null` | Action on tapping the state row. See [Tap Actions](#-tap-actions). When left unset (or set to `none`), tapping the state row instead toggles that entity's visibility on the graph — same as clicking its legend item. Hidden entities dim visually so you can tell what's off at a glance. |

#### 🎛️ Appearance

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `graph_type` | string | `"line"` | `line` / `step` / `bar`. Only available in Timeline mode — other chart modes ignore this. |
| `show_graph` | boolean | `true` | Show this entity on the graph |
| `show_line` | boolean | `true` | Show the line edge. Timeline mode only. |
| `show_fill` | boolean | `true` | Show the fill area below the line. Timeline mode only. |
| `show_range_band` | boolean | `false` | Draw a min/max shaded band behind the line showing the value range within each aggregation bucket. The line shows the average while the band shows how much the value fluctuated. See [Range Band](#-range-band). Timeline mode only. |
| `gradient` | boolean | `true` | Fade the fill from the entity color to transparent. Only applies when `show_fill` is true. Timeline mode only. |
| `show_points` | boolean | `false` | Show a dot at each data point. Timeline mode only. |
| `smooth` | boolean | `true` | Bezier curve smoothing. Timeline mode only. |
| `line_width` | number | `2.5` | Line thickness in pixels. Timeline mode only. |
| `show_extrema` | string | `"click"` | Min/Max labels: `never` / `click` / `always`. Timeline mode only. |
| `show_extrema_min` | boolean | `true` | Show the Min value label. Disable to show only the Max — useful for sensors where the minimum is always zero (solar power, rain, etc.). Timeline mode only. |
| `show_extrema_max` | boolean | `true` | Show the Max value label. Timeline mode only. |
| `extrema_show_timestamp` | boolean | `true` | Show the time the extreme value was recorded below each label. Disable for compact display showing only the value. Timeline mode only. |
| `extrema_color` | string | `null` | Custom font color for extrema labels. Accepts any CSS color or variable. Leave empty for theme default. Timeline mode only. |
| `extrema_font_size` | number | `13` | Font size of the extrema value in pixels. Timestamp text scales proportionally. Timeline mode only. |
| `extrema_bg_color` | string | `null` | Background color of the extrema label box. Combined with `extrema_bg_opacity`. Leave empty for theme default. Timeline mode only. |
| `extrema_bg_opacity` | number | `1` | Opacity of the extrema label background (`0` = transparent, `1` = solid). Set to `0` for floating text without a visible box. Timeline mode only. |
| `show_average` | boolean | `false` | Draw a dashed horizontal line at the mean value. Timeline mode only. |
| `break_on_null` | boolean | `false` | Break the line at long sensor outages instead of carrying the last known value across the gap. When `false` (default), the previous known value is carried forward indefinitely — the line stays continuous even during long `unavailable` / `unknown` periods. When `true`, short blips stay connected but outages longer than a threshold (default `min(3 × bucket, 30 minutes)`) appear as visible breaks in the line. Timeline mode only. Does **not** affect `value_transform` scripts that return `null` (those already drop their buckets before this logic runs). See [Break on Gaps](#-break-on-gaps). |
| `carry_forward_ms` | number | `null` | Advanced override for the carry-forward threshold in milliseconds. Takes effect regardless of `break_on_null`. Use this when you want a specific time window instead of the default auto threshold. Timeline mode only. |
| `show_state` | string/boolean | `true` | State row display: `true` (text), `false` (hidden), `"gauge"` (half-circle arc). See [Gauge Display](#-gauge-display). |
| `show_state_last` | boolean | `false` | **Legacy** — equivalent to `primary_state_as: last`. Still honored for backward compatibility. |
| `primary_state_as` | string | `null` | What appears as the big primary value in the state row. `null` (default) = live HA state. `last` = last aggregated graph point. `sum` / `avg` / `min` / `max` / `first` = the chosen aggregate over the visible window, shown as a clean number with no *"SUM"/"AVG"* label prefix. Useful for header-only entities (`show_graph: false`) that just display a computed number. |
| `show_timestamp` | boolean | `false` | When `primary_state_as` is `min`, `max`, `first`, or `last`, also show the time the value was recorded as a subdued suffix next to the main number. Useful for record-tracking cards (coldest day, peak solar, strongest wind, etc.). Format follows the card's `datetime_format` (or HA locale when set to `system`). Has no effect for `sum` / `avg` (no single timestamp applies). |
| `show_range_values` | boolean | `false` | Show the visible window's min and max as a subdued `(min → max)` suffix next to the primary value. Best paired with `show_graph: false` + `primary_state_as: min`/`max` for compact "records" cards (coldest day, peak solar, etc.) where the range otherwise lives only in a tooltip the user can't reach. Available for any aggregate (Last, First, Min, Max, Sum, Avg). When `show_range_band: true` is enabled on the entity, it uses the more accurate per-bucket band data; otherwise it falls back to the aggregate min/max over the visible window. Has no effect for live State (`primary_state_as: null`). |
| `name_position` | string | `null` | Controls how the entity name and primary value are arranged in the state row. `null` (default) = name to the left of the value (inline). `below` = value shown larger with the name centered underneath (ApexCharts-style, great for header-only entities and mobile layouts). |
| `show_second_state_as` | string | `null` | Show a secondary stat value next to the primary state. Options: `min`, `max`, `avg`, `sum`, `first`, `last`. Displays with the same styling as the primary value, with a small label prefix. |
| `show_trend_icon` | boolean | `true` | Show ▲▼⯇⯈ trend direction icon next to the state value. |
| `trend_period_hours` | number | `1` | Time window (in hours) for trend direction calculation. Set `0` for full range. |
| `show_in_legend` | boolean | `false` | Show a statistics row below the graph for this entity. Which stats are shown is controlled by `legend_stats`. |
| `legend_stats` | list | `["min","avg","max"]` | Which statistics to display in the legend row. Any combination of `min`, `avg`, `max`, `last`, `sum`. Requires `show_in_legend: true`. |
| `lower_bound` | string/number | `null` | Y axis minimum / gauge minimum. See [Bounds](#-bounds). |
| `upper_bound` | string/number | `null` | Y axis maximum / gauge maximum. See [Bounds](#-bounds). |
| `align_state` | string | `"left"` | State row position and alignment. Top variants: `left` / `center` / `right` (above the graph). Bottom variants: `bottom-left` / `bottom-center` / `bottom-right` (below the graph). |
| `stack_group` | string | `null` | Named group for stacked bars/lines. Entities with the same group name stack on top of each other; different groups sit side by side. Leave empty to stack all entities together (default). Requires `stacked: true`. See [Stacked Groups](#-stacked-groups). |
| `icon` | string | `null` | MDI icon in the state row, e.g. `mdi:thermometer` |
| `icon_size` | string | `null` | State row icon size, e.g. `18px` |
| `name_size` | string | `null` | State row name font size, e.g. `14px` |
| `state_size` | string | `null` | State row value font size, e.g. `13px` |
| `trend_icon_size` | string | `null` | Trend icon font size, e.g. `12px` |

#### 🎨 Colors

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `color` | string | `"#ff4757"` | Line and fill color. Use `threshold` to drive from color thresholds. Accepts `{{ }}` Jinja2 templates for dynamic server-side color resolution (e.g. `{{ state_attr('sensor.entity_colors','entities')['Temperature'] }}`). See [Color Templates](#-color-templates). |
| `point_colors` | string | `null` | Color of data point dots. Use `threshold` for per-point threshold color. Accepts `{{ }}` templates. |
| `icon_color` | string | `null` | State row icon color. Use `threshold` for dynamic color. Accepts `{{ }}` templates. |
| `state_color` | string | `null` | State row value text color. Use `threshold` for dynamic color. Accepts `{{ }}` templates. |
| `state_adaptive_color` | boolean | `false` | Automatically tint state value and icon with the entity's line color. Quick alternative to setting `state_color` and `icon_color` manually. |
| `rise_fall_colors` | object | `null` | Color by rise/fall direction. See [Rise/Fall Colors](#-risefall-colors). |
| `color_thresholds` | object | `null` | Color by value. See [Color Thresholds](#-color-thresholds). |

</details>

---

## 🎯 Chart Modes

<details>
<summary>Timeline, Scatter, Pie, Ranking, Heatmap, Calendar, Radial Bar, Polar Area, Radar</summary>

The `chart_mode` option at the card level controls the overall visualization. Each mode takes over the entire graph area.

### Timeline *(default)*

Classic time-series chart. Entities can individually be `line`, `step`, or `bar`. All Timeline-specific options (axes, grid, stacked, scroll, annotations, offset, zoom) are available.

![image2](images/bar.png)

### Scatter

Plots the first entity on the X axis and the second on the Y axis to reveal correlations. Exactly 2 entities required.

![Scatter Example](images/scatter-example.png)

```yaml
chart_mode: scatter
entities:
  - entity: sensor.temperature
    color: "#ff4757"
  - entity: sensor.humidity
    color: "#378ADD"
```

Points are matched by timestamp (5-minute tolerance). Older dots are faded, newer dots are vivid. X/Y axes show entity value ranges, not time.

### Pie Chart

Centered chart showing proportional shares. Slice labels show the actual value with the unit (or percentage in Ranking mode).

**Style presets** — choose how the pie ring looks:

- **Classic** — full pie with no center hole
- **Thick** — wide donut ring, plenty of fill
- **Donut** *(default)* — standard donut with a center hole
- **Thin** — narrow ring, modern minimal look

**3D effect** — set `pie_3d: true` to add depth, perspective and a subtle highlight on top. Works with any preset.

**Slice spacing** — set `pie_spacing` (in degrees, 0–15) for visible gaps between slices. Spaced slices automatically get rounded corners. Only applies to donut styles, not Classic.

**Center total** — when `show_tooltip_total: true`, the total value appears in the donut hole. Disable to make Classic a true full pie.

**Label and color customization** — fine-tune the look of slice labels and the center total to match your theme:

- `pie_label_font_size` — slice value label size in pixels (leave empty for auto)
- `pie_label_color` — slice value label color (CSS color or `var(--…)`; auto = white)
- `pie_center_font_size` — center total size in pixels (leave empty for auto)
- `pie_center_color` — center total color; the small "Total" sub-label inherits this with reduced opacity

All four accept theme variables, so `pie_label_color: var(--accent-color)` updates with your active theme.

**Past dates** — using a date picker to scroll back to a period with no data shows an empty ring with a friendly "No data" message instead of returning today's value.

![Pie Example](images/pie-example.png)

```yaml
chart_mode: pie
height: 200
pie_style: donut       # classic | thick | donut | thin
pie_spacing: 4         # 0-15 degrees, gap between slices
pie_3d: true           # depth/perspective effect
pie_label_font_size: 14
pie_label_color: var(--primary-text-color)
pie_center_font_size: 32
pie_center_color: var(--accent-color)
show_tooltip_total: true  # center total
entities:
  - entity: sensor.hvac_energy
    aggregate_func: sum
    color: "#E24B4A"
  - entity: sensor.lighting_energy
    aggregate_func: sum
    color: "#EF9F27"
  - entity: sensor.kitchen_energy
    aggregate_func: sum
    color: "#1D9E75"
```

### Ranking

Horizontal bars sorted by value (highest first). Each bar shows name, proportional width, value, unit, and share percentage.

![Ranking Example](images/ranking-example.png)

```yaml
chart_mode: ranking
height: 200
entities:
  - entity: sensor.bedroom_temp
    color: "#E24B4A"
  - entity: sensor.living_room_temp
    color: "#378ADD"
  - entity: sensor.kitchen_temp
    color: "#EF9F27"
```

### Heatmap

Days × hours color grid. Each cell represents one hour of one day, colored by intensity. Only the first entity is used.

![Heatmap Example](images/heatmap-example.png)

```yaml
chart_mode: heatmap
hours_to_show: 168
height: 250
entities:
  - entity: sensor.temperature
    color: "#ff4757"
```

The color range can be controlled three ways:
- **Automatic** — min/max derived from data
- **Manual bounds** — set entity `lower_bound` / `upper_bound` for a fixed color scale
- **Color thresholds** — enable `color_thresholds` for multi-color heatmaps (e.g., blue → green → red)

### Calendar

GitHub-contribution-style weekly grid. Each cell = one day. Only the first entity is used.

![Calendar Example](images/calendar-example.png)

```yaml
chart_mode: calendar
hours_to_show: 720
height: 200
entities:
  - entity: sensor.energy_daily
    aggregate_func: sum
    color: "#1D9E75"
```

### Radial Bar

Concentric progress arcs — each entity is a ring showing its value as a percentage of a defined range. The center displays the average.

![Radial Bar Example](images/radialbar-example.png)


```yaml
chart_mode: radialbar
height: 250
entities:
  - entity: sensor.living_room_temp
    color: "#ff4757"
    lower_bound: 0
    upper_bound: 40
  - entity: sensor.bedroom_temp
    color: "#378ADD"
    lower_bound: 0
    upper_bound: 40
  - entity: sensor.garage_temp
    color: "#2ecc71"
    lower_bound: 0
    upper_bound: 40
```

Set `lower_bound` / `upper_bound` per entity to define the 0–100% range. If not set, the entity's historical min/max from the current time window is used. Supports color thresholds for dynamic ring colors.

### Polar Area

Equal-angle slices with variable radius — larger values produce bigger slices. Like a pie chart but comparing magnitudes instead of shares.

![Polar Area Example](images/polararea-example.png)

```yaml
chart_mode: polararea
height: 250
entities:
  - entity: sensor.living_room_temp
    color: "#ff4757"
  - entity: sensor.bedroom_temp
    color: "#378ADD"
  - entity: sensor.garage_temp
    color: "#2ecc71"
```

Includes concentric grid circles for reference. Percentage labels appear on slices ≥ 4%. The center shows the total.

### Radar

Spider/polygon chart where each entity forms one spoke. The filled polygon reveals the overall sensor profile at a glance.

![Radar Example](images/radar-example.png)

```yaml
chart_mode: radar
height: 300
entities:
  - entity: sensor.temperature
    name: "Temperature"
    lower_bound: 0
    upper_bound: 40
  - entity: sensor.humidity
    name: "Humidity"
    lower_bound: 0
    upper_bound: 100
  - entity: sensor.co2
    name: "CO₂"
    lower_bound: 400
    upper_bound: 2000
  - entity: sensor.pm25
    name: "PM2.5"
    lower_bound: 0
    upper_bound: 50
```

Requires at least 3 entities. Each entity's value is normalized to its `lower_bound` / `upper_bound` range. Polygon grid rings provide reference levels. Colored dots at each vertex show the exact position, with value labels nearby. Supports color thresholds for per-dot colors.

### State Timeline

```yaml
type: custom:statistics-graph-chart-card
chart_mode: state_timeline
hours_to_show: 24
state_timeline_corner_radius: 3       # 0 = sharp, higher = rounder
entities:
  - entity: binary_sensor.window_living_room
    name: Living Room
    tap_action:                        # tap a row to open more-info or run an action
      action: more-info
    state_map:
      - value: "off"
        label: "Closed"
        color: "#e74c3c"
      - value: "on"
        label: "Open"
        color: "#5dade2"
```

Displays horizontal colored bars showing state changes over time — one row per entity. Entity names appear on the left, state labels inside each segment when wide enough. Hover for a tooltip showing state name, duration, and time range. Works with `binary_sensor`, `input_boolean`, `input_select`, and any entity with a `state_map`.

**v2.28 additions:**
- **Corner radius** is configurable via `state_timeline_corner_radius` (0–20 px, default 3). Set to `0` for sharp edges or use higher values for pill-shaped segments.
- **Horizontal scroll** works via `max_visible_interval` + `scroll_mode`, just like in regular Timeline. Load a week of history (`hours_to_show: 168`) but only show 24 hours on screen at once (`max_visible_interval: 24`) — the chart scrolls to reveal the rest.
- **Tap action** is supported on each row. Because every row in state_timeline corresponds to exactly one entity and its segments fill the row, tapping a row naturally means "do something with this entity". If the entity has a `tap_action` set it fires; otherwise a standard more-info dialog opens.

### Chart Mode Compatibility

Not all card options apply to every mode. The visual editor hides irrelevant options automatically.

| Feature | Timeline | State Timeline | Scatter | Pie | Ranking | Radial Bar | Polar Area | Radar | Heatmap | Calendar |
|---------|----------|----------------|---------|-----|---------|------------|------------|-------|---------|----------|
| Y / X axes | ✅ | X only | ✅ | — | — | — | — | — | Own axes | Own axes |
| Grid | ✅ | — | ✅ | — | — | — | Grid circles | Polygon grid | — | — |
| Stacked | ✅ | — | — | — | — | — | — | — | — | — |
| Offset | ✅ | — | — | — | — | — | — | — | — | — |
| Annotations | ✅ | — | — | — | — | — | — | — | — | — |
| Zoom brush | ✅ | — | — | — | — | — | — | — | — | — |
| Scroll | ✅ | ✅ | — | — | — | — | — | — | — | — |
| Sparkline | ✅ | — | — | — | — | — | — | — | — | — |
| Range Band | ✅ | — | — | — | — | — | — | — | — | — |
| Entity limit | ∞ | ∞ | 2 | ∞ | ∞ | ∞ | ∞ | 3+ | 1 | 1 |
| Entity graph_type | line/step/bar | — | — | — | — | — | — | — | — | — |
| lower/upper_bound | Y axis range | — | — | — | — | 0–100% range | — | Normalization | Color scale | Color scale |

</details>

---

## 📚 Feature Guides

<details>
<summary>Date Picker, Energy Sync, Zoom, Sparkline, Annotations, and 18 more</summary>

<details>
<summary><strong>📅 Date Picker</strong></summary>

A built-in date navigation panel that lets users browse historical data by Day, Week, Month, or Year — without leaving the dashboard.

### Setup

```yaml
type: custom:statistics-graph-chart-card
show_date_picker: true
date_picker_position: top
entities:
  - entity: sensor.temperature_living
    color: "#ff6b35"
```

### Navigation

The date picker bar shows the current period label with arrow buttons to move forward/backward:

![Date Sync Example](images/Datepicker.gif)

- **D / W / M / Y** — switch between Day, Week, Month, and Year views
- **◀ ▶** — navigate to the previous/next period
- **📅** — open the calendar popup for direct date selection

### Calendar & Presets

Click the calendar icon to open a panel with:

- **Calendar grid** — click two dates to select a custom range
- **Quick presets** — Today, Yesterday, This/Last Week, This/Last Month, This/Last Year, Last 7 Days, Last 30 Days, Last 12 Months

The calendar stays open after selection so you can adjust the range. Click the 📅 icon again to close it.

### Group Sync

Cards with the same `date_picker_group` share their date selection. **You don't need a visible date picker on every card** — only one card needs `show_date_picker: true`. Other cards in the same group will follow along automatically.

```yaml
# Card 1: Has the visible date picker — this is the "controller"
show_date_picker: true
date_picker_group: bedroom

# Card 2: No visible picker — just follows Card 1
date_picker_group: bedroom

# Card 3: Also follows Card 1
date_picker_group: bedroom
```

Changing the date on Card 1 updates all three cards. Cards 2 and 3 show no picker UI but their data range follows the group selection.

This is ideal for dashboards where you want one date picker controlling multiple charts without repeating the picker bar on every card.

### Customizing Modes

Control which period buttons appear with `date_picker_modes`:

```yaml
# Show only Month and Year
date_picker_modes:
  - month
  - year

# Lock to Month — buttons hidden, navigation centered
date_picker_modes:
  - month
```

When only one mode is listed, the D/W/M/Y buttons are hidden entirely and the navigation (◀ label ▶) is centered for a minimal look. The 📅 calendar icon stays visible on the right.

### Window Step

`date_picker_step` controls how many units make up one "window". Default `1` = the legacy behavior (each click moves one day, one week, one month, etc.). When you set it higher, the picker becomes a **rolling N-unit window** and prev/next buttons jump a full N units at a time.

```yaml
# Last 4 weeks, prev/next jumps 4 weeks
show_date_picker: true
date_picker_step: 4
date_picker_modes:
  - week
```

```yaml
# Last 30 days, prev/next jumps 30 days
date_picker_step: 30
date_picker_modes:
  - day
```

The label adapts automatically: `step > 1` shows the date range (`Mar 11 – Apr 7`), `step = 1` keeps the existing single-period labels (`April 2026`, `Apr 1 – Apr 7`).

> **Editor:** General Settings → Overlays → *Window Step* (appears next to *Visible Modes* when the date picker is enabled)

### Behavior

| Period | X-axis range | Live updates |
|---|---|---|
| **Today** | 00:00 → end of day | ✅ Active |
| **Yesterday** | 00:00 → 23:59 | ❌ Paused |
| **This Week** | Monday 00:00 → end of week | ✅ Active |
| **Last 7 Days** | 7 days ago → now | ✅ Active |
| **Custom range** | Start → End | Depends on whether end is today |

### Editor

General Settings → Overlays → **Date Picker** toggle. Position and Group options appear on the same row. The **Group** field is always editable — even when the Date Picker toggle is off — so you can assign a group to cards that don't show their own picker. When enabled, a **Visible Modes** section appears below with D/W/M/Y checkboxes.

### Notes

- Cannot be used together with `energy_date_sync` — enabling one disables the other
- Date picker state is persisted in `localStorage` and restored on page reload
- When viewing the current period, the X-axis extends to the end of the period with empty space after the current time
- Cards with only `date_picker_group` (no `show_date_picker`) use their normal `hours_to_show` until a sync event arrives from a card in the same group

</details>

<details>
<summary><strong>⚡ Energy Date Sync</strong></summary>

Syncs the card's time range with Home Assistant's Energy dashboard date picker or the [energy-period-selector-plus](https://github.com/flixlix/energy-period-selector-plus) custom card.

![Energy Date Sync Example](images/picker.gif)

### Setup

```yaml
type: custom:statistics-graph-chart-card
energy_date_sync: true
entities:
  - entity: sensor.energy_consumption
    color: "#ff4757"
    aggregate_func: sum
  - entity: sensor.solar_production
    color: "#2ecc71"
    aggregate_func: sum
```

Place the card on the same dashboard as an Energy date picker. When the user selects a day, week, month, or custom range, this card automatically updates to show the same period.

### Behavior

| Date selection | X-axis range | Live updates |
|---|---|---|
| **Today** | 00:00 → current time | ✅ Active — graph updates in real time |
| **Yesterday** | 00:00 → 23:59 | ❌ Paused — historical data is frozen |
| **This week** | Monday 00:00 → current time | ✅ Active |
| **Last week** | Monday 00:00 → Sunday 23:59 | ❌ Paused |
| **This month** | 1st 00:00 → current time | ✅ Active |
| **Custom range** | Start → End (clamped to now if end is in the future) | Depends on whether end is today |

### Compatible with

- HA's built-in Energy dashboard date picker (DAY / WEEK / MONTH / YEAR)
- [energy-period-selector-plus](https://github.com/flixlix/energy-period-selector-plus) custom card
- Any card that uses HA's energy data collection system

### Editor

General Settings → Overlays → **Energy Date Sync** toggle.

### Notes

- When `energy_date_sync` is active, it overrides `hours_to_show` and the interval picker selection
- The card subscribes to HA's energy data collection on the WebSocket connection — no polling needed
- If the Energy panel hasn't loaded yet, the card retries every 2 seconds for up to 60 seconds

</details>

<details>
<summary><strong>📅 Show Full Period</strong></summary>

Extends the X-axis to cover a complete calendar period, leaving empty space after the current time. A dashed vertical "now" line marks where live data ends.

```yaml
graph_start_hour: 0
hours_to_show: 24
show_full_period: true    # X-axis: 00:00 → 23:59, empty after now
```

The end of the period is determined by `graph_start`:

| `graph_start` | X-axis extends to |
|---------------|-------------------|
| off | End of today (next midnight) |
| `week` | End of week (next Monday 00:00) |
| `month` | End of month (1st of next month) |
| `year` | End of year (Jan 1st next year) |

### With Energy Date Sync

`show_full_period` also works with `energy_date_sync: true`. When the energy date picker selects a current period (today, this week, this month), the X-axis extends to the full period end. Past periods display in full as before.

```yaml
energy_date_sync: true
show_full_period: true    # energy picker "This Month" → X-axis: Apr 1 → May 1
```

This is especially useful for:
- **Imported data** (energy, gas) that arrives with a few days delay — the graph shows the gap instead of filling it with the last known value
- **Day comparison** with offset — today's card shows a partial day with empty space; yesterday's card (offset: 24) shows a complete day
- **Weekly/monthly dashboards** — see the full period at a glance with the "now" marker
- **Energy dashboard** — combine with `energy_date_sync` to see the full billing period

> **Editor:** General Settings → **X-Axis** tab → *Show Full Period* checkbox

![full Example](images/full1.png)

</details>

<details>
<summary><strong>📅 Long-Range Views</strong></summary>

Visualize data over weeks, months, and years with calendar-aware grouping and native HA statistics.

### Weekly, Monthly, and Yearly Grouping

```yaml
group_by: week
graph_start: month         # this month's weeks
aggregate_func: change     # consumption per week
graph_type: bar
```

```yaml
group_by: month
graph_start: year          # start from Jan 1
```

```yaml
group_by: year
hours_to_show: 87600       # ~10 years
aggregate_func: change     # annual consumption
graph_type: bar
```

When `group_by` is set to `date`, `week`, `month`, or `year`, the card fetches data using native HA statistics periods (`period: 'day'`, `'week'`, `'month'`). Year mode fetches monthly data and aggregates client-side. This enables the `change` aggregate field and bypasses the database retention limit — you can display a full year of data even if your recorder purge is set to 10 days.

### Auto-Routing to Long-Term Statistics

Even in `interval` mode with short ranges (`hours_to_show ≤ 24`), the card auto-routes to long-term statistics in two cases:

1. **Any entity declares `statistic_id` explicitly** — the user vouches that the entity has long-term statistics available. Useful for entities that exist only in the statistics database (Gazpar, Linky, etc.) or for forcing the route.
2. **`hours_to_show > 240`** (≈ 10 days, the typical recorder retention) — statistics is the only source that can serve the range, so the card switches automatically.

In both cases the route is **conditional on every relevant entity having long-term statistics available** — meaning a `state_class` of `measurement`, `total`, or `total_increasing`, or an explicit `statistic_id`. If any entity in the card lacks LTS, the route falls back to the regular history API to keep that entity working.

When the requested range exceeds 10 days but some entities lack LTS, a console warning is printed once listing the offending entities and explaining how to enable `state_class` in HA.

### Graph Start Anchoring

When `graph_start` is set, `hours_to_show` is ignored — the calendar period directly determines the start:

| Value | Behavior |
|-------|----------|
| `week` | Start from Monday 00:00 |
| `month` | Start from the 1st of the month |
| `year` | Start from January 1st |

> **Editor:** General Settings → Display → Graph Navigation → *Graph Start*

### Graph Start: Tomorrow

`graph_start: tomorrow` sets the window to tomorrow 00:00 → end of day — ideal for next-day spot prices (Nord Pool, EPEX, Tibber) via `data_attribute`. The window extends into the future automatically without `show_full_period`.

```yaml
type: custom:statistics-graph-chart-card
card_header: Tomorrow Spot Prices
graph_start: tomorrow
group_by: hour
entities:
  - entity: sensor.nord_pool_fi_contract_current_price
    data_attribute: tomorrow_hourly
    data_time_field: start
    data_value_field: value
    graph_type: bar
    decimals: 2
    unit: c/kWh
```

### X-Axis Interval

Manual control over tick spacing:

```yaml
x_axis_interval: 2h    # Every 2 hours (00:00, 02:00, 04:00…)
x_axis_interval: 1d    # Daily (midnight)
x_axis_interval: 1w    # Weekly (Mondays)
x_axis_interval: 1M    # Monthly (1st of month)
```

Available presets in the editor: Auto, 1H–12H, 1D, 2D, 7D, 1W, 2W, 1M, 3M.

> **Editor:** General Settings → X-Axis → *X Axis Interval*

### Grid Customization

Control the appearance of horizontal (Y) and vertical (X) grid lines independently.

```yaml
y_grid_style: solid      # dashed (default), solid, dotted, long-dash
y_grid_width: 0.5         # thickness in px (default: 1)
y_grid_color: "rgba(255,255,255,0.1)"  # any CSS color or {{ template }}
y_grid_opacity: 0.3       # 0–1 (default: 0.15)

x_grid_style: dotted
x_grid_width: 0.5
x_grid_color: "var(--divider-color)"
x_grid_opacity: 0.3
```

> **Editor:** Y Axis tab → Grid section, X Axis tab → Grid section

### Smart X-Axis Labels

The X-axis automatically adapts to the `group_by` setting:

- **Week** — Ticks on Mondays: "3 Mar", "10 Mar"
- **Month** — Ticks on the 1st: "Jan", "Feb" (with year when spanning multiple years)
- **Date** — Daily ticks: "3 Mar", "4 Mar"
- **Hour** — Hourly ticks; midnight shows date instead of "00:00"

In `interval` mode, midnight labels also show the date for any view longer than 12 hours.

</details>

<details>
<summary><strong>🎛️ Gauge Display</strong></summary>

Replace the numeric state row with a half-circle gauge arc. Set `show_state: gauge` on any entity.

![Gauge Example](images/gauge-example.png)

```yaml
entities:
  - entity: sensor.temperature
    show_state: gauge
    color: "#ff4757"
    lower_bound: 15    # gauge minimum
    upper_bound: 30    # gauge maximum
```

The gauge arc sweeps 270° from `lower_bound` to `upper_bound`. The center shows the current value + unit, bottom edges show min/max labels. Multiple gauge entities display side-by-side: 1 entity = large gauge, 2+ = compact.

`color_thresholds` work with gauge — the arc color changes dynamically based on value.

The graph below the gauge continues to show the historical trend as usual.

</details>

<details>
<summary><strong>✨ Sparkline Mode</strong></summary>

Card-level `sparkline: true` strips all chrome and renders ultra-compact inline graphs. Only available in Timeline mode.

![Sparkline Example](images/sparkline-example.png)

```yaml
sparkline: true
entities:
  - entity: sensor.temperature
    color: "#ff4757"
  - entity: sensor.humidity
    color: "#378ADD"
grid_options:
  columns: 12
  rows: 2
```

Each entity becomes one row: name + value + trend icon on the left, tiny graph on the right. Removed: header, icon, toolbar, axes, grid, tooltip, legend, annotations. Preserved: entity colors, line smoothing, fill, trend icons, live streaming, color thresholds, and rise/fall colors.

</details>

<details>
<summary><strong>🔍 Brush Zoom</strong></summary>

Click and drag on any Timeline mode graph to zoom into a specific time range. No configuration needed — it's always available.

![Sparkline Example](images/brush.gif)

### How it works

1. **Click and drag** horizontally — a blue selection overlay appears with formatted timestamps at both edges
2. **Release** — the graph zooms into the selected range, recalculating Y axis, grid, statistics (Min/Avg/Max), extrema labels, and legend values
3. **Reset** — double-click the graph, or click the **"Reset zoom"** button in the top-right corner

**Key details:**

- **No API calls on zoom** — the full dataset is preserved in memory; zooming only filters and re-renders existing data. Reset is instant.
- **Progressive zoom** — zoom again within an already-zoomed view to drill deeper into spikes or anomalies
- **Touch support** — works on mobile: touch and drag to select
- **Minimum 15px selection** — prevents accidental zoom from regular clicks or taps
- **Time formatting** — selection labels show time only for ranges under 24H, date + time for longer ranges
- **Interval picker aware** — changing the time range via the interval picker resets any active zoom and fetches fresh data

Timeline mode only.

### Mobile Touch Behavior

On phones and tablets, touch gestures separate tooltip exploration from brush zoom:

| Gesture | Action |
|---|---|
| **Tap** | Tooltip appears instantly with crosshair and values |
| **Quick slide** | Tooltip follows finger across the graph |
| **Hold on bar** | Tooltip + bar highlight stay visible as long as finger is held |
| **Long press (600ms) + drag** | Brush zoom selection starts |
| **Lift finger** | Tooltip and highlights clear |

Holding still for 600ms prepares zoom but does not activate it — zoom only starts when the finger moves. This prevents the tooltip from disappearing while exploring a single data point.

</details>

<details>
<summary><strong>📊 Stacked Mode</strong></summary>

Card-level `stacked: true` stacks entities on top of each other (Timeline mode only). Bar entities stack vertically. Line/area entities stack as bands. Entities on the same Y axis and graph type are stacked together. The tooltip shows a "Total" row.

```yaml
stacked: true
entities:
  - entity: sensor.solar_production
    color: "#f39c12"
  - entity: sensor.grid_import
    color: "#e74c3c"
  - entity: sensor.battery_discharge
    color: "#3498db"
```

### Stacked Groups

By default, all bar entities stack into a single column. Use `stack_group` to create **named groups** — entities within the same group stack on top of each other, while different groups sit side by side.

```yaml
stacked: true
group_by: date
entities:
  - entity: sensor.solar_production
    graph_type: bar
    stack_group: energy
    color: "#2ecc71"
  - entity: sensor.grid_import
    graph_type: bar
    stack_group: energy
    color: "#e74c3c"
  - entity: sensor.cost_peak
    graph_type: bar
    stack_group: cost
    color: "#f39c12"
  - entity: sensor.cost_offpeak
    graph_type: bar
    stack_group: cost
    color: "#3498db"
```

This renders two side-by-side bar groups per time slot: an "energy" stack (solar + grid) and a "cost" stack (peak + off-peak). Backward compatible — if no `stack_group` is set, all entities stack together as before.

> **Editor:** Per-entity → Graph tab → *Stack Group* text field (visible when Stacked is enabled)

</details>

<details>
<summary><strong>🏷️ Compact Legend</strong></summary>

Card-level `show_legend: true` adds a compact color-coded entity name key below the graph. Just colored dots and names — no values, no stats. Wraps to multiple lines on narrow cards.

```yaml
show_legend: true
entities:
  - entity: sensor.memory
    name: "Memory"
    color: "#f39c12"
    show_state: false
  - entity: sensor.disk
    name: "Disk"
    color: "#85b7eb"
    show_state: false
  - entity: sensor.cpu
    name: "CPU"
    color: "#00bcd4"
    show_state: false
```

This produces: `● Memory  ● Disk  ● CPU` in a centered wrapping row below the graph. Combine with `show_state: false` on entities to maximize graph area while still identifying colors.

For per-entity statistics (Min, Avg, Max, Last), use the entity-level **Legend** toggle instead — see [Entity Legend Stats](#per-entity-legend-stats).

![tempo](images/temp.gif)

</details>

<details>
<summary><strong>📊 Per-Entity Legend Stats</strong></summary>

Each entity's Legend toggle (`show_in_legend: true`) now lets you choose which statistics to display. Select any combination of Min, Avg, Max, and Last.

```yaml
entities:
  - entity: sensor.temperature
    show_in_legend: true
    legend_stats:
      - avg
      - last
  - entity: sensor.humidity
    show_in_legend: true
    legend_stats:
      - min
      - max
```

The editor shows four checkboxes (Min, Avg, Max, Last) inside the Legend section. Default is `[min, avg, max]` for backward compatibility.

</details>

<details>
<summary><strong>⬇️ State Row Position</strong></summary>

Entity state rows can now be placed **below** the graph instead of above. The `align_state` option accepts six positions:

| Value | Position |
|---|---|
| `left` *(default)* | Above graph, left-aligned |
| `center` | Above graph, centered |
| `right` | Above graph, right-aligned |
| `bottom-left` | Below graph, left-aligned |
| `bottom-center` | Below graph, centered |
| `bottom-right` | Below graph, right-aligned |

```yaml
entities:
  - entity: sensor.temperature
    align_state: bottom-left
  - entity: sensor.humidity
    align_state: left         # stays above the graph
```

Mix and match — some entities above, some below. Useful when you want the graph to be the first thing visible, with values underneath.

</details>

<details>
<summary><strong>↕️ Independent Y2 Axis</strong></summary>

The primary (left) and secondary (right) Y axis labels can be toggled independently:

```yaml
show_y_axis: true       # primary — left side
show_y2_axis: false     # secondary — right side hidden
entities:
  - entity: sensor.temperature
    y_axis: primary
  - entity: sensor.humidity
    y_axis: secondary     # still plotted, just no labels on right
```

Useful when the secondary axis labels are distracting or when you want to maximize horizontal graph space. Both entities continue to be plotted against their respective axes — only the labels are hidden.

</details>

<details>
<summary><strong>↕️ Independent Y-Axis</strong></summary>

Overlay sensors with completely different units on a single graph for trend comparison. Each `independent` entity gets its own hidden scale based on its data's min/max range. No axis labels are shown — only the visual trend matters.

```yaml
entities:
  - entity: sensor.temperature
    y_axis: primary          # Left axis, shared scale, visible labels
    color: "#ff4757"
  - entity: sensor.humidity
    y_axis: secondary        # Right axis, shared scale, visible labels
    color: "#378ADD"
  - entity: sensor.illuminance
    y_axis: independent      # Own hidden scale: 0–10000 lux
    color: "#f39c12"
  - entity: sensor.pressure
    y_axis: independent      # Own hidden scale: 980–1020 hPa
    color: "#2ecc71"
```

There is no limit on the number of independent entities. Each one is scaled individually. Primary and secondary entities continue to share their respective axis scales.

> **Editor:** Per-entity → **Data** tab → *Y Axis* dropdown → "Independent"

</details>

<details>
<summary><strong>🔀 Value Transform</strong></summary>

Apply a JavaScript expression to every data point before graphing. The transform has access to the current value and series-level statistics, making it possible to normalize, compare, and reshape data in ways that weren't possible before.

### Available variables

| Variable | Description |
|---|---|
| `x` | Current data point value |
| `first` | First value in the visible time window |
| `last` | Last value in the visible time window |
| `min` | Minimum value across the series |
| `max` | Maximum value across the series |
| `avg` | Average value across the series |
| `index` | Position of the current point (0, 1, 2…) |

All variables are computed after `value_factor` is applied, before the transform runs.

### Normalize to zero

Display cumulative meter readings as relative consumption starting from zero:

```yaml
entities:
  - entity: sensor.gas_meter
    value_transform: "return x - first;"
```

A gas meter reading `2200, 2210, 2225, 2240` becomes `0, 10, 25, 40`.

### Splitting a sensor into export/import

A common use case: a single power sensor reports positive values for export and negative values for import. Use two entity entries with different transforms to separate them:

```yaml
entities:
  - entity: sensor.grid_power
    name: "Grid Export"
    color: "#2ecc71"
    value_transform: "return x > 0 ? x : 0"

  - entity: sensor.grid_power
    name: "Grid Import"
    color: "#e74c3c"
    value_transform: "return x < 0 ? -x : 0"
```

### Common expressions

| Expression | What it does |
|---|---|
| `return x - first` | Normalize to zero (cumulative → relative) |
| `return ((x - first) / first) * 100` | Percentage change from start |
| `return (x - min) / (max - min)` | Min-max normalization (scale to 0–1) |
| `return x - avg` | Deviation from average |
| `return x > 0 ? x : 0` | Keep only positive values (zero out negatives) |
| `return x < 0 ? -x : 0` | Keep only negative values, flip to positive |
| `return Math.abs(x)` | Absolute value |
| `return x * 1.1` | Add 10% markup |
| `return x - 273.15` | Convert Kelvin to Celsius |
| `return (x * 9/5) + 32` | Convert Celsius to Fahrenheit |
| `return Math.round(x / 100) * 100` | Round to nearest hundred |

### Editor

Entity → General → **Value Transform** — a monospace text input field. Enter the expression directly (e.g., `return x - first`).

### Notes

- The expression must be valid JavaScript and include a `return` statement
- If the expression errors or returns a non-number, the original value is used unchanged
- Applied to every data point individually — both historical and live values
- Works with all chart modes, aggregation functions, and other entity options
- Context variables (`first`, `min`, etc.) are only available when processing a full data series — in the state row live value display, all context variables equal `x`

</details>

<details>
<summary><strong>📏 Range Band</strong></summary>

The Range Band feature draws a shaded min/max area behind each line entity, showing how much the value fluctuated within each aggregation bucket.

![Range Band Example](images/rangeband-example.png)

### How it works

When `points_per_hour` aggregates multiple raw data points into a single graph point, the displayed value is typically the average (or whichever `aggregate_func` you've chosen). The range band shows the **full min → max spread** of raw values that were combined — so you can see both the trend and the volatility.

```yaml
entities:
  - entity: sensor.outdoor_temperature
    show_range_band: true
    color: "#ff4757"
  - entity: sensor.indoor_temperature
    show_range_band: false
    color: "#378ADD"
```

### Use cases

- **Temperature**: narrow band = stable climate, wide band = fluctuating (e.g. HVAC cycling)
- **Energy**: see consumption spikes vs steady draw within each time bucket
- **Sensor noise**: distinguish real signal changes from noisy sensor readings

### Editor

Entity → General → **Range Band** toggle (next to Show Average).

### Tooltip

When hovering, an additional row shows the range: `Range: 21.2 → 22.8 °C`.

</details>

<details>
<summary><strong>🕳️ Break on Gaps</strong></summary>

When a sensor goes `unavailable` or `unknown`, the card normally keeps the line continuous by carrying the last known value forward across the gap. That's great for short blips (brief WiFi drops, bucket-level reporting irregularity) but can hide genuine multi-hour outages behind a flat line. The per-entity `break_on_null` option lets you opt in to a visible break instead.

```yaml
entities:
  - entity: sensor.steady_sensor
    # default — continuous line, last known value carried across any gap

  - entity: sensor.flakey_sensor
    break_on_null: true
    # short blips still connect, but longer outages appear as gaps

  - entity: sensor.very_specific
    break_on_null: true
    carry_forward_ms: 900000   # advanced — 15 min threshold
```

### Behavior

| Setting | Effect |
|---|---|
| `break_on_null: false` *(default)* | Carry-forward runs indefinitely within the visible window. No null-induced gaps, ever. The long-standing default behavior. |
| `break_on_null: true` | Short sample gaps (bucket-level blips, irregular reporting, brief drops) stay connected. Longer outages — default threshold `min(3 × bucket width, 30 minutes)` — appear as visible breaks in the line. |
| `carry_forward_ms: N` *(YAML, advanced)* | Override the threshold with an explicit value in milliseconds. Applies regardless of the `break_on_null` setting. |

### Why not just "break at every null"?

A pure "zero carry-forward" mode turns out to be too aggressive on real-world sensors. When bucket width is finer than the sensor's natural sample interval (a common setup at high `points_per_hour`), dozens of buckets between two real samples end up empty even though the sensor is perfectly healthy. The time-based threshold distinguishes *"I'm waiting for the next sample"* from *"the device has been gone for a while"* — which is the distinction users actually want to see.

### Editor

Entity → General → **Break on Gaps** toggle (next to Show Average and Range Band). Only shown in Timeline mode.

### Notes

- Does **not** affect `value_transform` scripts that return `null` to drop a bucket — those nulls are removed from the series before carry-forward logic runs.
- Works independently per entity, so you can mix well-behaved sensors (continuous line) with flakey ones (visible gaps) on the same card.

</details>

<details>
<summary><strong>📌 Annotations</strong></summary>

Add reference lines, event markers, and highlight bands to the graph (Timeline mode only). Configure via the editor (General Settings → Overlays → Annotations) or YAML.

![Anno Example](images/anno.png)
![Anno Example](images/anno2.png)

```yaml
annotations:
  - type: threshold       # horizontal dashed line
    value: 22.5
    label: "Target"
    color: "#1D9E75"
  - type: threshold       # dynamic value from entity
    value: sensor.climate_setpoint
    label: "Setpoint"
    color: "#f39c12"
  - type: band            # horizontal shaded band
    value: 20
    value_end: 23
    label: "Comfort zone"
    color: "#1D9E75"
  - type: band            # dynamic band from entity attributes
    value: sensor.comfort.min_temp
    value_end: sensor.comfort.max_temp
    label: "Dynamic comfort"
    color: "#3498db"
  - type: event           # vertical marker at state transitions
    entity: binary_sensor.heating
    state: "on"
    label: "Heating on"
    color: "#D85A30"
  - type: span            # vertical band for active periods
    entity: binary_sensor.heating
    state: "on"
    color: "#D85A30"
```

| Type | Description |
|------|-------------|
| `threshold` | Horizontal dashed line at a fixed value, entity state, or entity attribute |
| `band` | Horizontal shaded band between `value` and `value_end`. Both accept numbers, entity IDs, or `entity.attribute` paths |
| `event` | Vertical marker — entity-driven (at each state transition) or manual (fixed timestamp) |
| `span` | Vertical shaded band — entity-driven (duration in a specific state) or manual (fixed start/end timestamps) |

| Option | Applies to | Description |
|--------|-----------|-------------|
| `opacity` | All types | Opacity of the annotation (0–1). Default: 0.15 for bands/spans, 1 for lines/events |
| `show_values` | threshold, band | Show numeric values alongside the label. Default: true |
| `label` | All types | Text label displayed on the annotation |
| `color` | All types | Color of the annotation line, fill, or marker |

Threshold and band values accept: `22.5` (number), `sensor.x` (entity state), `sensor.x.attribute` (entity attribute with nested path support).

**Live updates**: when a threshold or band value references a sensor or input helper, the annotation updates instantly as soon as that entity's state changes — no need to wait for the next data refresh. Combine with a HA template sensor to get seasonal or month-based thresholds that automatically move over time:

```yaml
# configuration.yaml
template:
  - sensor:
      - name: Solar Target
        state: >
          {% set m = now().month %}
          {% if m in [6,7,8] %}8000
          {% elif m in [4,5,9,10] %}5000
          {% else %}2000
          {% endif %}
        unit_of_measurement: kWh
```

```yaml
# card
annotations:
  - type: threshold
    value: sensor.solar_target
    label: Seasonal target
    color: "#1D9E75"
```

Use `show_values: false` on any threshold or band to hide the value label while keeping the line/band visible. When enabled (default), the numeric value appears alongside the label — or by itself if no label is set:

```yaml
annotations:
  - type: band
    value: 20
    value_end: 25
    label: "Comfort"
    color: "#1D9E75"
    show_values: false    # band visible, no text labels
```

**Manual timestamps** — event markers and time spans can use fixed timestamps instead of tracking an entity. Switch between Entity and Manual source in the editor, or set directly in YAML:

```yaml
annotations:
  - type: span
    start: "2026-04-15T08:00:00"
    end: "2026-04-15T18:00:00"
    label: "Day shift"
    color: "#ff9800"
  - type: event
    time: "2026-04-15T12:00:00"
    label: "Noon"
    color: "#e74c3c"
```

**Opacity** — control the prominence of each annotation with the `opacity` option (0–1). Applies to all types: fill opacity for bands and spans, stroke opacity for threshold lines and event markers:

```yaml
annotations:
  - type: band
    value: 18
    value_end: 24
    color: "#1D9E75"
    opacity: 0.3        # more prominent than default 0.15
  - type: threshold
    value: 30
    color: "#e74c3c"
    opacity: 0.5         # semi-transparent line
```

**Jinja2 templates** — annotation fields `start`, `end`, `time`, `value`, `value_end`, and `label` accept Jinja2 templates. Values update automatically when referenced entities change:

```yaml
annotations:
  - type: threshold
    value: "{{ states('sensor.target_temperature') | float }}"
    label: "{{ states('input_text.target_label') }}"
    color: "#e74c3c"
  - type: span
    start: "{{ states('input_datetime.shift_start') }}"
    end: "{{ states('input_datetime.shift_end') }}"
    label: "Shift"
    color: "#ff9800"
```

</details>

<details>
<summary><strong>🔗 Tooltip Sync</strong></summary>

Synchronize hover crosshairs across multiple cards on the same dashboard page. When you hover over one card, all synced cards show their tooltip and crosshair at the **same timestamp** — even if they display different entities or different time ranges.

This is a **card-level** feature (not entity-level), because what's shared is a timestamp, not an entity value. All entities on a synced card show their values at that moment simultaneously.

![Sync Example](images/sync.gif)

### Setup

Enable Tooltip Sync on each card you want to participate, and give related cards the same Sync Group name:

```yaml
# Card 1 — Bedroom Temperature
type: custom:statistics-graph-chart-card
tooltip_sync: true
tooltip_sync_group: "bedroom"
entities:
  - entity: sensor.bedroom_temperature

# Card 2 — Bedroom Humidity (syncs with Card 1)
type: custom:statistics-graph-chart-card
tooltip_sync: true
tooltip_sync_group: "bedroom"
entities:
  - entity: sensor.bedroom_humidity

# Card 3 — Kitchen Temperature (independent)
type: custom:statistics-graph-chart-card
tooltip_sync: true
tooltip_sync_group: "kitchen"
entities:
  - entity: sensor.kitchen_temperature

# Card 4 — Energy (no sync at all)
type: custom:statistics-graph-chart-card
entities:
  - entity: sensor.energy
```

In this setup:
- Cards 1 and 2 sync with each other (both in "bedroom" group)
- Card 3 syncs only with other "kitchen" cards
- Card 4 has no sync — hovering over it broadcasts nothing, and it ignores broadcasts from others

### Sync Group Rules

| Sync Group value | Behavior |
|---|---|
| `"bedroom"` | Syncs only with other cards that have `tooltip_sync_group: "bedroom"` |
| `"kitchen"` | Syncs only with "kitchen" cards |
| *(empty / not set)* | Syncs with **all** tooltip-synced cards on the page, regardless of their group |
| `tooltip_sync: false` | Card does not participate in sync at all |

> **Tip:** The group name is completely arbitrary — use room names, floor numbers, or any string you like. It just needs to match across the cards you want to link.

### How It Works

1. You hover over Card A → a `sgc-tooltip-sync` event is dispatched on `window` containing the hovered timestamp, the sync group name, and the card's unique instance ID
2. All other cards with Tooltip Sync enabled listen for this event
3. If the group matches (or either card has no group), the receiving card calls `_showTooltipAtTime(timestamp)` — which positions its crosshair and tooltip at the matching time position
4. When you move the mouse away, a hide event clears all synced tooltips

Cards with different `hours_to_show` ranges still sync correctly — the shared language is the **timestamp**, not the pixel position. A card showing 24H and a card showing 7D will both jump to 2:35 PM if that's where your mouse is.

Timeline mode only.

</details>

<details>
<summary><strong>↔️ Time Offset</strong></summary>

Compare the same sensor across different time periods by adding multiple entity entries with different `offset` values. Each offset shifts that entity's data backward in time while keeping it aligned on the same graph.

```yaml
hours_to_show: 168
entities:
  - entity: sensor.energy_consumption
    name: "This week"
    offset: 0
    color: "#ff4757"
  - entity: sensor.energy_consumption
    name: "Last week"
    offset: 168
    color: "#378ADD"
  - entity: sensor.energy_consumption
    name: "2 weeks ago"
    offset: 336
    color: "#2ecc71"
```

### How it works

- `offset: 168` means "fetch data from 168 hours (7 days) before the current display window"
- The fetched data is time-shifted forward to align with the current window on the X axis
- All rendering features work at full quality — line, bar, step, fill, gradient, points, tooltips, stacking, zoom
- Each entity with an offset gets its own API call with the correct time range

### Common offset values

| Offset | Period |
|---|---|
| `24` | Yesterday |
| `168` | Last week |
| `336` | 2 weeks ago |
| `720` | Last month (~30 days) |
| `8760` | Last year |

### Dynamic Offset via Helper Entity

Instead of a fixed number, you can point `offset` to any HA entity whose state is a number (in hours). The card reads the entity's current state and re-fetches history automatically when it changes.

```yaml
entities:
  - entity: sensor.energy_consumption
    name: "Current"
  - entity: sensor.energy_consumption
    name: "Comparison"
    offset: input_number.comparison_offset
    color: "#378ADD"
```

This works with any entity type — `input_number`, template sensors, or any sensor that outputs a numeric state. Combine with HA template sensors for fully dynamic comparisons:

```yaml
# In HA configuration.yaml
template:
  - sensor:
      - name: "Dynamic Offset"
        state: "{{ 24 if now().weekday() < 5 else 168 }}"
        unit_of_measurement: "h"
```

### Editor

Entity → General → Data Settings → **Offset** (in hours).

### Notes

- Offset entities do not receive live WebSocket updates (they show historical data)
- The state row, sparkline, and gauge correctly display the last value from the offset time window — not the live entity state
- Works with all chart modes that support multiple entities
- Can be combined with `value_transform`, `value_factor`, and all other entity options
- Each offset generates a separate cache entry, so switching between views is fast

</details>

<details>
<summary><strong>🔮 Forecast Horizon</strong></summary>

Some sensors expose a **forecast value** — their current state represents what is predicted for **N hours in the future**, not what is happening right now. Typical examples:

- `sensor.solcast_pv_forecast_leistung_in_1_stunde` — PV power expected in 1 hour
- A template sensor whose state is "temperature in 3 hours"
- A weather forecast exposed as a numeric future-hour prediction

Plotting these directly is misleading: the line shows each prediction at the time it was recorded, not at the time it is predicting. `forecast_horizon: N` fixes this by **shifting each recorded data point forward by N hours** on the X-axis so every point lands at the moment it is forecasting.

```yaml
type: custom:statistics-graph-chart-card
graph_start_hour: now
show_full_period: true
entities:
  - entity: sensor.solcast_pv_forecast_leistung_in_1_stunde
    name: "Forecast +1h"
    forecast_horizon: 1
```

The result: a line that extends **1 hour into the future** past the "now" marker, representing the forecast for each upcoming moment. The X-axis end is automatically extended by the largest `forecast_horizon` across all entities so shifted points stay visible.

### Matching the horizon to the sensor

The `forecast_horizon` value should match the actual prediction horizon the sensor represents:

| Sensor | `forecast_horizon` |
|---|---|
| `solcast_pv_forecast_leistung_in_1_stunde` | `1` |
| `solcast_pv_forecast_leistung_in_8_stunden` | `8` |
| Custom "temperature in 30 minutes" | `0.5` |

Setting a value that doesn't match the sensor's real horizon will still shift the line — but the displayed time no longer corresponds to what the sensor is actually predicting.

### Negative horizon — overlay tomorrow's forecast onto today

Some forecast integrations (Solcast PV, EPEX spot prices, weather APIs) expose **future data through entity attributes** — a single sensor whose `attributes` contain an array of timestamped points covering the next 24–48 hours. Combined with `data_attribute`, you can plot this future data directly. But what if you want to see **tomorrow's forecast on today's chart timeline** for an at-a-glance comparison?

A **negative `forecast_horizon`** shifts each point *backward* in time. Setting `-24` moves tomorrow's points 24 hours earlier so they appear at today's clock positions:

```yaml
type: custom:statistics-graph-chart-card
show_legend: true
entities:
  - entity: sensor.solcast_pv_forecast_tomorrow
    data_attribute: detailedHourly
    data_time_field: period_start
    data_value_field: pv_estimate
    name: "Tomorrow's forecast (shown today)"
    forecast_horizon: -24
```

The X-axis stays anchored to today — only the data slides into view. Combine with the live PV sensor (no horizon) on the same chart to see today's reality next to tomorrow's prediction, both aligned to the same hours.

### Combining with `offset`

`forecast_horizon` and `offset` are **orthogonal**:

- `offset` shifts the fetch window **backward** (for past-period overlay comparison)
- `forecast_horizon` shifts the display **forward** (positive) **or backward** (negative)

Both can be used on the same entity. Example: overlay yesterday's 1-hour forecast sensor onto today's timeline, shifted 1h forward:

```yaml
entities:
  - entity: sensor.solcast_pv_forecast_leistung_in_1_stunde
    offset: 24            # fetch yesterday's recordings
    forecast_horizon: 1   # show them shifted 1h forward
    name: "Yesterday's +1h forecast"
```

### Editor

Entity → **Advanced** tab → *Forecast Horizon* (in hours, supports decimals — including negative values).

### Notes

- Leave empty (or `0`) to disable — the sensor plots at its recording time as before
- The fetch window is extended backward by the largest horizon so past recordings can be retrieved and shifted forward into the visible future range
- Works with live state updates — new recordings appear on the chart at recording time + horizon
- Multiple entities can use different horizons — the X-axis is extended to cover the largest one

</details>

<details>
<summary><strong>🏷️ Template Names</strong></summary>

Entity names support HA-style `{{ }}` templates that resolve dynamically using `hass.states`:

```yaml
name: "{{ state_attr('sensor.room', 'friendly_name') }}"
name: "{{ states('sensor.power') }} W"
name: "{{ state_attr('sensor.temperature', 'device_class') | capitalize }}"
name: "Room: {{ state_attr('sensor.room', 'friendly_name') | upper }}"
```

### Supported functions

| Function | Description |
|----------|-------------|
| `states('entity_id')` | Current state value |
| `state_attr('entity_id', 'attribute')` | Entity attribute value |
| `is_state('entity_id', 'value')` | Returns `"true"` or `"false"` |

### Supported filters

Filters are chained with `|`, just like Jinja2:

| Filter | Example | Result |
|--------|---------|--------|
| `capitalize` | `temperature` → | `Temperature` |
| `upper` | `salon` → | `SALON` |
| `lower` | `SALON` → | `salon` |
| `title` | `living room` → | `Living Room` |
| `trim` | `" text "` → | `"text"` |
| `int` | `"22.5"` → | `"22"` |
| `float` | `"22"` → | `"22"` |
| `round(n)` | `22.567 \| round(1)` → | `"22.6"` |
| `replace('a','b')` | `replace('_',' ')` | Replaces all occurrences |
| `default('val')` | Fallback if empty/unknown | |
| `truncate(n)` | Cuts to n chars + `…` | |

Multiple filters can be chained: `{{ state_attr('sensor.x', 'type') | replace('_', ' ') | title }}`

</details>

<details>
<summary><strong>🔋 Battery Icon</strong></summary>

Display a battery level indicator on the card. When a header exists (title or icon), the battery appears in the top-right corner. When there's no header, it appears on the right side of the state row.

![Battery Example](images/battery.png)

```yaml
battery_entity: sensor.temperature_battery
battery_low_threshold: 20
```

Color adapts to battery level:

| Level | Color |
|-------|-------|
| >50% | Green |
| 25–50% | Yellow |
| low–25% | Orange |
| Below threshold | Red |

The low threshold defaults to 20% and accepts a number, entity ID (`sensor.x`), or entity attribute (`sensor.x.attribute`). Hover shows the entity friendly name and exact percentage.

The icon and percentage text scale proportionally with the **Header & Battery Size** setting (`card_header_size`). This applies in both header and state row positions.

> **Editor:** General Settings → **Display** tab → *Battery*

</details>

<details>
<summary><strong>📡 Attribute Data Source</strong></summary>

Read chart data directly from an entity attribute instead of history. The attribute must contain an array of objects with time and value fields. The X-axis automatically extends into the future when data contains future timestamps.

Ideal for energy spot prices, weather forecasts, and solar production predictions. No history or statistics API calls are made for these entities.

```yaml
entities:
  - entity: sensor.epex_spot_price
    data_attribute: data
    data_time_field: start_time
    data_value_field: price_per_kwh
    value_factor: 2
    graph_type: step
    name: "Electricity Price"
```

Common configurations:

| Integration | `data_attribute` | `data_time_field` | `data_value_field` |
|---|---|---|---|
| EPEX Spot | `data` | `start_time` | `price_per_kwh` |
| Nordpool | `raw_today` | `start` | `value` |
| Tibber | `price_info` | `startsAt` | `total` |
| Forecast.Solar | `detailedForecasts` | `period_start` | `pv_estimate` |

Compatible with existing `value_factor`, `value_transform`, `aggregate_func`, and `group_by`. The time and value field names support nested paths via dot notation (e.g. `forecast.0.temperature`).

### Time Unit

By default, the time field is parsed as an ISO date string. Set `data_time_unit` to interpret it differently — perfect for sensors that expose monthly summaries, hourly profiles, day-of-year datasets, or Unix timestamps without generating artificial timestamps.

| Unit | Range | Behavior |
|---|---|---|
| `iso` (default) | string / epoch ms | `new Date(t)` — existing behavior |
| `epoch_seconds` | number | Unix timestamp in seconds |
| `epoch_ms` | number | Unix timestamp in milliseconds |
| `month_of_year` | 1..12 | First day of that month in `data_time_year` (default: current year) |
| `day_of_year` | 1..366 | That day in `data_time_year` |
| `week_of_year` | 1..53 | Monday of that ISO week in `data_time_year` |
| `hour_of_day` | 0..23 | That hour of today |

Example — a sensor exposing monthly yield expectations as `[{Month: 1, Expectation: 320}, {Month: 2, Expectation: 489}, ...]`:

```yaml
type: custom:statistics-graph-chart-card
group_by: month
graph_start: year
hours_to_show: 8760
entities:
  - entity: sensor.sma_month_yield_expectation
    data_attribute: Expectation
    data_time_field: Month            # 1..12
    data_value_field: Expectation
    data_time_unit: month_of_year     # interpret as Jan..Dec
    graph_type: bar
    aggregate_func: max
```

Renders 12 bars labelled Jan–Dec on the X-axis. Tooltip shows the actual month + value. All other features (date picker, group_by, fill, theming) work normally because the parser converts the numeric category into a real `Date` internally.

> **Editor:** Per-entity → **Data** tab → *Attribute Data Source* → *Time Unit* dropdown and *Reference Year* input

> **Editor:** Per-entity → **Data** tab → *Attribute Data Source*

</details>

<details>
<summary><strong>🔄 Invert Bars (Butterfly Charts)</strong></summary>

Per-entity `invert: true` draws bars downward from the zero line. Tooltip, state row, and extrema labels show positive values. Combined with `stacked: true`, creates butterfly charts for energy import/export, network in/out, and similar comparisons.

```yaml
stacked: true
entities:
  - entity: sensor.grid_import
    graph_type: bar
    aggregate_func: change
    color: "#f39c12"
    name: Import
  - entity: sensor.grid_export
    graph_type: bar
    aggregate_func: change
    invert: true
    color: "#3498db"
    name: Export
```

Inverted entities automatically form their own stacking group — normal bars stack upward from zero, inverted bars stack downward independently. The Y-axis expands symmetrically to accommodate both directions.

When used with **line or area charts** (not just bars), the fill correctly stops at the zero baseline: mirrored lines fill upward to zero, normal lines fill downward to zero, and series that cross zero get a clean positive/negative split.

> **Editor:** Per-entity → **Data** tab → *Invert (Mirror)* checkbox

</details>

<details>
<summary><strong>🔌 External Statistics</strong></summary>

Display data from imported statistics that don't have a regular entity in Home Assistant. This covers energy data from integrations like Gazpar, Linky, Tibber, and others that import directly into HA's statistics database.


### Background

Some HA integrations don't create `sensor.*` entities. Instead, they write data directly into the `statistics` and `statistics_meta` database tables using HA's `async_import_statistics()` API. These statistics have IDs with a colon separator (e.g. `gazpar:gazpar_consumption`) and are visible on the Energy dashboard and the built-in Statistics Graph card, but not in the entity registry.

### Setup

Use `statistic_id` instead of (or alongside) `entity`:

```yaml
entities:
  - entity: ""
    statistic_id: "gazpar:gazpar_consumption"
    name: "Gas Consumption"
    color: "#f39c12"
    aggregate_func: sum
  - entity: ""
    statistic_id: "linky:linky_consumption"
    name: "Electricity"
    color: "#378ADD"
    aggregate_func: sum
  - entity: sensor.indoor_temperature
    name: "Temperature"
    color: "#ff4757"
```

You can mix external statistics with regular entities on the same card.

### How it works

- The card detects external statistics by checking for a `:` in the `statistic_id`
- Data is fetched via HA's `recorder/statistics_during_period` WebSocket API — the same API the Energy dashboard uses
- Since there is no live state, the state row displays the last known value from the statistics data
- All card features work: tooltip, legend, axes, stacking, offset, zoom, color thresholds, etc.

### Editor

Entity → General → **Statistic ID** input field (monospace, below the entity picker). Set the entity picker to empty and fill in the statistic ID.

### Finding your statistic IDs

1. Go to **Developer Tools → Statistics** in HA
2. Search for the integration name (e.g. "gazpar")
3. The statistic ID is shown in the list (e.g. `gazpar:gazpar_consumption`)

</details>

</details>

---

## 💡 Examples

<details>
<summary>Ready-to-use YAML configurations</summary>

### Basic: Single Sensor

```yaml
type: custom:statistics-graph-chart-card
card_header: Bedroom
hours_to_show: 12
entities:
  - entity: sensor.bedroom_temperature
    name: Temperature
    color: "#ff6b35"
    icon: mdi:thermometer
```

---

### 🌡️ Multi-Entity with Dual Axes

Combine temperature and humidity on the same card without the scales conflicting.

<!-- IMAGE 3: Card with temperature line (primary) and humidity line (secondary axis) -->

```yaml
type: custom:statistics-graph-chart-card
card_header: Climate
card_icon: mdi:home-thermometer
hours_to_show: 24
lower_bound_secondary: "~0"
upper_bound_secondary: "~100"
entities:
  - entity: sensor.temperature
    name: Temperature
    color: "#ff6b35"
    y_axis: primary
    icon: mdi:thermometer

  - entity: sensor.humidity
    name: Humidity
    color: "#00bcd4"
    y_axis: secondary
    icon: mdi:water-percent
```

---

### ⚡ Bar Chart with Legend

```yaml
type: custom:statistics-graph-chart-card
card_header: Energy Today
entities:
  - entity: sensor.daily_energy
    name: Consumption
    graph_type: bar
    color: "#2ecc71"
    show_in_legend: true
    aggregate_func: sum
    group_by: hour
```

---

### 🎨 Color Thresholds

Colorize the graph based on value ranges. Two independent settings control the behavior:

- **Direction** — which axis the colors are painted along:
  - `vertical` *(default)* — Y-axis gradient. The entire chart is colored based on value height.
  - `horizontal` — per-segment coloring along the time axis. Each line segment gets the color matching its data value.

- **Transition** — how colors change at threshold boundaries:
  - `smooth` *(default)* — gradual interpolation between adjacent threshold colors.
  - `hard` — instant color switch exactly at the threshold value.

<!-- IMAGE 4: Temperature graph with gradient color from blue (cold) through green to red (hot) -->

```yaml
type: custom:statistics-graph-chart-card
entities:
  - entity: sensor.outdoor_temperature
    name: Outdoor Temp
    color: threshold
    state_color: threshold
    color_thresholds:
      enabled: true
      direction: vertical   # or: horizontal
      transition: smooth     # or: hard
      values:
        - value: 0
          color: "#3498db"
        - value: 15
          color: "#2ecc71"
        - value: 25
          color: "#f39c12"
        - value: 35
          color: "#e74c3c"
```

All four direction × transition combinations are available from the editor under Colors → Color Thresholds.

Setting `color: threshold` propagates threshold colors to the state row dot as well. Setting `state_color: threshold` colors the displayed value text.

**Gradient fill is threshold-aware.** When `gradient: true` is enabled alongside `color_thresholds`, the fill area under the line is rendered as a vertical gradient whose colors match the line — the gradient stops sample threshold colors at chart top, zero line, and chart bottom. For a chart that crosses zero with two threshold bands (e.g. purple above zero, green below), the fill blends from purple at the top through transparent at the zero line down to green at the bottom, just like the line itself.

---

### 📈 Rise/Fall Colors

Color each graph segment green when rising and red when falling — without needing to define any value thresholds. The trend icon on the state row reflects the same direction. `trend_period_hours` controls how sensitive the detection is.

```yaml
type: custom:statistics-graph-chart-card
entities:
  - entity: sensor.stock_price
    name: Price
    rise_fall_colors:
      enabled: true
      increase: "#2ecc71"
      decrease: "#e74c3c"
      stable: "#95a5a6"
    show_trend_icon: true
    trend_period_hours: 2
```

---

### 🎨 Color Templates

Use Jinja2 templates in any color field to manage colors centrally. Create a single template sensor with all your entity colors, and every card updates when you change it.

**Setup: Create a central color sensor**

```yaml
# configuration.yaml → template section
template:
  - sensor:
      - name: "Entity Colors"
        unique_id: entity_colors_map
        state: "ok"
        attributes:
          entities: >-
            {{
              {
                "Temperature": "#FF6B6B",
                "Humidity": "#2ecc71",
                "Solar": "#f1c40f"
              }
            }}
```

**Usage in card YAML:**

```yaml
entities:
  - entity: sensor.temperature
    color: "{{ state_attr('sensor.entity_colors','entities')['Temperature'] | default('#ff4757') }}"
    icon_color: "{{ states('input_select.theme_accent') }}"
```

Templates are evaluated server-side by HA via WebSocket subscriptions — colors update automatically when dependencies change, with no polling. In the editor, typing `{{` in any color field dims the picker automatically.

Works with `color`, `point_colors`, `icon_color`, `state_color`, and all card-level color options (`y_axis_color`, `x_axis_color`, `y_grid_color`, `x_grid_color`, `card_icon_color`).

---

### ➖ Average Line

Draw a dashed reference line at the mean value over the visible time window. Useful for spotting trends at a glance.

<!-- IMAGE: Average line shown on a temperature graph as a dashed horizontal line with a value label -->

```yaml
type: custom:statistics-graph-chart-card
hours_to_show: 24
entities:
  - entity: sensor.outdoor_temperature
    name: Temperature
    color: "#ff6b35"
    show_average: true

  # Multiple entities each show their own average in their own color
  - entity: sensor.indoor_temperature
    name: Indoor
    color: "#00bcd4"
    show_average: true
```

---

### 🔗 Attribute Reading

Read a specific attribute instead of the main entity state. Supports dot notation for nested paths.

```yaml
type: custom:statistics-graph-chart-card
entities:
  # Simple attribute
  - entity: weather.home
    name: Humidity
    attribute: humidity
    icon: mdi:water-percent

  # Nested attribute (e.g. first forecast entry)
  - entity: weather.home
    name: Forecast Temp
    attribute: forecast.0.temperature
    icon: mdi:thermometer
```

---

### 🔀 State Map — Non-Numeric Entities

Use `state_map` to graph entities with string states like `input_boolean`, `binary_sensor`, or `input_select`. States are mapped to numbers in the order they are listed, starting at 0.

**The Y-axis automatically shows the original state names instead of numeric indexes** — so a washing machine graph displays `idle`, `running`, `done` on the axis, not `0`, `1`, `2`. Tooltips and state rows match.

You can optionally provide friendly display labels with the `label` field — useful when the raw state is technical (`armed_home`) but you want a cleaner axis (`Home`):

```yaml
type: custom:statistics-graph-chart-card
entities:
  # binary_sensor → 0 (off) / 1 (on), axis shows "off" / "on"
  - entity: binary_sensor.front_door
    name: Front Door
    color: "#9b59b6"
    graph_type: step
    state_map:
      - value: "off"
      - value: "on"

  # With friendly labels — axis shows "Idle" / "Running" / "Done"
  - entity: sensor.washing_machine
    name: Washing Machine
    graph_type: step
    state_map:
      - value: "idle"
        label: Idle
      - value: "running"
        label: Running
      - value: "done"
        label: Done

  # input_select → 0 / 1 / 2 / 3
  - entity: input_select.heating_mode
    name: Heating Mode
    state_map:
      - value: "off"
      - value: "eco"
      - value: "comfort"
      - value: "boost"
```

In the visual editor, the State Map textarea accepts a simple `value, label` syntax — one per line:

```
off, Idle
on, Running
```

> Auto-detected for `binary_sensor`, `input_boolean`, and any `input_select` entity in step mode — you don't need to define a `state_map` for those, the card detects available states automatically and labels the axis accordingly.

---

### 📏 Fixed Value Reference Line

Draw a flat horizontal line at the current value of an entity. Useful for showing targets or limits alongside historical data.

```yaml
type: custom:statistics-graph-chart-card
entities:
  - entity: sensor.room_temperature
    name: Temperature
    color: "#ff6b35"

  - entity: input_number.target_temperature
    name: Target
    color: "#2ecc71"
    fixed_value: true
    show_fill: false
    line_width: 1.5
```

---

### 〰️ Soft Bounds

Use a `~` prefix to create a soft bound — the axis will prefer the value but expand if data exceeds it. Hard bounds (no prefix) force the axis edge regardless of data.

```yaml
type: custom:statistics-graph-chart-card
entities:
  - entity: sensor.battery_level
    name: Battery
    lower_bound: "~0"    # prefer 0 as minimum; expands if data goes below
    upper_bound: "~100"  # prefer 100 as max; expands if data exceeds
```

---

### 📡 Dynamic Y Axis Bounds

Bind the Y axis min/max to another sensor for a fully dynamic range.

```yaml
type: custom:statistics-graph-chart-card
entities:
  - entity: sensor.power_output
    name: Power
    lower_bound: 0
    upper_bound: sensor.max_capacity
```

---

### 👆 Tap Actions

Trigger actions when tapping an entity's state row.

```yaml
type: custom:statistics-graph-chart-card
entities:
  # Open entity detail dialog
  - entity: sensor.temperature
    tap_action:
      action: more-info

  # Navigate to another dashboard
  - entity: sensor.energy
    tap_action:
      action: navigate
      navigation_path: /lovelace/energy

  # Call a service
  - entity: binary_sensor.pump
    tap_action:
      action: call-service
      service: switch.toggle
      service_data:
        entity_id: switch.pump

  # Fire DOM event (browser_mod popup, YAML only)
  - entity: sensor.power
    tap_action:
      action: fire-dom-event
      browser_mod:
        service: browser_mod.popup
        data:
          content:
            type: custom:mini-graph-card
            entity: sensor.power
```

---

### 🌅 Dynamic Graph Hours

Filter data to specific hours each day using sensor values. Ideal for solar panels (sunrise to sunset) or business hours.

```yaml
type: custom:statistics-graph-chart-card
graph_start_hour: sensor.sunrise_hour
graph_end_hour: sensor.sunset_hour
hours_to_show: 168
show_date_picker: true
entities:
  - entity: sensor.solar_power
```

Create template sensors that output fractional hours:

```yaml
template:
  - sensor:
      - name: "Sunrise Hour"
        unique_id: sunrise_hour
        state: >
          {% set dt = state_attr('sun.sun', 'next_rising') | as_datetime | as_local %}
          {{ dt.hour + dt.minute / 60 }}
      - name: "Sunset Hour"
        unique_id: sunset_hour
        state: >
          {% set dt = state_attr('sun.sun', 'next_setting') | as_datetime | as_local %}
          {{ dt.hour + dt.minute / 60 }}
```

When viewing multiple days, data outside the specified hours is hidden and lines break naturally between days. Both `graph_start_hour` and `graph_end_hour` accept fixed numbers (`6`, `22`, `6.5` for 06:30) or entity IDs.

---

### ⏩ Sparse Data with Points Per Hour

For sensors that update infrequently (e.g. weather), use a higher `points_per_hour` with forward-fill. Empty buckets inherit the last known value, producing a clean step-line instead of scattered dots.

```yaml
type: custom:statistics-graph-chart-card
points_per_hour: 12
hours_to_show: 24
entities:
  - entity: weather.home
    attribute: humidity
    name: Humidity
    smooth: false  # step-like appearance is more accurate for infrequent updates
```

---

### 🎚️ Interval Picker & Attribute Switcher

Add on-card controls for quick time range switching and live attribute exploration — no need to open the editor.

```yaml
type: custom:statistics-graph-chart-card
card_header: Weather Station
hours_to_show: 24
show_interval_picker: true
interval_picker_position: left
show_attribute_list: true
attribute_list_position: right
entities:
  - entity: weather.home
    name: Temperature
    attribute: temperature
    color: "#ff6b35"

  - entity: weather.home
    name: Humidity
    attribute: humidity
    color: "#00bcd4"
```

The interval picker displays buttons for the default set: 1H, 2H, 4H, 8H, 12H, 24H, and 7D. Clicking a button temporarily overrides `hours_to_show`; clicking again deselects it and returns to the original range.

To customize which buttons appear, use `interval_options`:

```yaml
# Show only the intervals you need — fits on one row on mobile
show_interval_picker: true
interval_options:
  - "2H"
  - "12H"
  - "24H"
  - "7D"
  - "30D"
```

Available labels: `1H`, `2H`, `4H`, `8H`, `12H`, `24H`, `3D`, `7D`, `14D`, `30D`, `90D`, `6M`, `1Y`. The editor also provides a **Visible Intervals** checkbox grid under the Interval Picker toggle (General Settings → Overlays).

The attribute list shows a dropdown per entity with a color-coded dot. Select any numeric attribute to instantly re-graph with that data — the graph, state row, and tooltip all update live.

Both controls share a single toolbar row and wrap automatically on narrow cards.

---

### 🔍 Scrollable Graph

Load a wide time range but show only a portion at a time — scroll to explore.

```yaml
type: custom:statistics-graph-chart-card
card_header: Weekly Overview
hours_to_show: 168        # 7 days of data
max_visible_interval: 24  # show 24h at a time
scroll_mode: wheel         # or: scrollbar
entities:
  - entity: sensor.temperature
    color: "#ff6b35"
```

The graph starts scrolled to the right (most recent data). Y-axis labels stay fixed while the graph content scrolls underneath. Scroll position is preserved across HA state updates.

| `scroll_mode` | Behavior |
|---------------|----------|
| `scrollbar` | Thin visible scrollbar *(default)* |
| `wheel` | Mouse wheel scrolls horizontally, no visible scrollbar |

On mobile/touch devices, swipe always works regardless of the scroll mode setting.

> 💡 Combines well with the **Interval Picker** — select "7D" to get a wide range, then scroll through it with a 6-hour visible window.

---

### ↔️ Icon Position

Place the header icon on the right side for a different layout feel.

```yaml
type: custom:statistics-graph-chart-card
card_header: Living Room
card_icon: mdi:thermometer
card_icon_position: right   # default: left
entities:
  - entity: sensor.temperature
    color: "#ff6b35"
```

---

### 🏆 Full Example

A complete card showing most features together.

<!-- IMAGE 6: Full-featured card with header, icon, multiple entities, legend, and grid -->

```yaml
type: custom:statistics-graph-chart-card
card_header: Home Climate
card_icon: mdi:home-thermometer
card_icon_color: "#ff6b35"
align_header: left
hours_to_show: 24
points_per_hour: 6
height: 180
show_grid: true
show_tooltip: true
animate_graph: false
update_interval: 60

entities:
  - entity: sensor.living_temperature
    name: Temperature
    color: "#ff6b35"
    icon: mdi:thermometer
    y_axis: primary
    show_in_legend: true
    show_extrema: click
    show_average: true
    show_trend_icon: true
    trend_period_hours: 2
    decimals: 1
    gradient: true
    state_adaptive_color: true
    color_thresholds:
      enabled: true
      transition: smooth
      values:
        - value: 18
          color: "#3498db"
        - value: 22
          color: "#2ecc71"
        - value: 28
          color: "#e74c3c"

  - entity: sensor.living_humidity
    name: Humidity
    color: "#00bcd4"
    icon: mdi:water-percent
    y_axis: secondary
    show_in_legend: true
    decimals: 0
    lower_bound: "~0"
    upper_bound: "~100"
```

</details>

---

## 📖 Reference

<details>
<summary>Aggregation functions, date formats, bounds, tap actions</summary>

### 🧮 Aggregation Functions

Controls how raw data points within each time bucket (interval / hour / date / week / month / year) are combined into a single graph value. Set per-entity via `aggregate_func`.

| Value | Formula | Best for |
|-------|---------|----------|
| `avg` *(default)* | Σ(values) ÷ count — the mean | Smooth lines for measurement sensors (temperature, power, humidity) |
| `min` | Lowest value in the bucket | Coldest temperature, minimum pressure, etc. |
| `max` | Highest value in the bucket | Peak temperature, max demand |
| `first` | Value at the start of the bucket (earliest) | Opening price, state at midnight |
| `last` | Value at the end of the bucket (latest) | Closing price, current state of a slowly-changing sensor |
| `median` | Middle value when sorted | Noise-resistant center (better than avg for data with outliers) |
| `sum` | Σ(values) | Totals over already-rate quantities (e.g. €/hour pricing × hours) |
| `delta` | **max − min** | Spread / range — how much the value **fluctuated** inside the bucket |
| `change` | **Σ of positive step differences** | Total **accumulated increase** over the bucket — ideal for monotonic counters (energy meters, water meters) because counter resets (jumps to zero) are ignored |
| `diff` | *Legacy alias for `change`* — YAML only (not shown in the editor dropdown since v2.27), behaves identically | Kept for backward compatibility with existing configs; new configs should use `change` |

#### Worked example — 1-hour bucket with values `[10, 25, 5, 30, 28]` recorded in this order

| Function | Result | How |
|---|---|---|
| `avg` | 19.6 | (10 + 25 + 5 + 30 + 28) / 5 |
| `min` | 5 | Smallest |
| `max` | 30 | Largest |
| `first` | 10 | First in time |
| `last` | 28 | Last in time |
| `median` | 25 | Middle of sorted `[5, 10, 25, 28, 30]` |
| `sum` | 98 | 10 + 25 + 5 + 30 + 28 |
| `delta` | 25 | 30 − 5 (max − min) |
| `change` | 40 | Positive step differences only: (10→25 = +15) + (25→5 ignored) + (5→30 = +25) + (30→28 ignored) = 15 + 25 |

*Note: `change` adds up **only the positive jumps** between consecutive points. If your counter goes `0 → 5 → 3 → 8`, the result is `5 + 5 = 10`, not `8`. The `5 → 3` drop is treated as a reset and ignored, the `3 → 8` rise counts.*

#### When your sensor is a counter (`state_class: total_increasing`)

Use `aggregate_func: change` with `group_by: date`, `week`, or `month`. This triggers an additional optimization: the card uses HA's **native `change` field** from long-term statistics, which is both faster and more accurate across counter resets than computing from raw history.

```yaml
entities:
  - entity: sensor.energy_meter
    aggregate_func: change
    graph_type: bar
group_by: date
hours_to_show: 720    # 30 days of daily consumption bars
```

---

### 🕐 Date Formats

Set `datetime_format` at the card level to control how timestamps appear on the X-axis, tooltips, and extrema labels. `system` follows HA's locale setting. All other formats are applied regardless of locale — useful when your dashboard is shared across regions or when you need a more compact display.

> **Note:** In earlier versions, `datetime_format` was an entity-level option. It has been promoted to a card-level setting. Entity-level values still work for backward compatibility and override the card setting when present.

#### Smart X-Axis Labels

When using the default `system` format, the X-axis automatically adapts to the visible time range. If the graph spans multiple calendar days, midnight ticks (00:00) display the date (e.g. "28 Mar") instead of the time — making it easy to identify day boundaries at a glance. All other ticks show `HH:mm` as usual. This behavior is inspired by ApexCharts.

When a custom `datetime_format` is set, all ticks use that format uniformly.

The number of ticks on the X-axis is calculated dynamically based on the label width, which depends on font size (`x_axis_font_size`) and the chosen format. Shorter formats like `HH:mm` fit more ticks; longer formats like `DD/MM HH:mm` produce fewer ticks automatically.

| Value | Example output |
|-------|---------------|
| `system` | Follows HA locale |
| `DD/MM` | 24/01 |
| `MM/DD` | 01/24 |
| `DD/MM HH:mm` | 24/01 14:35 |
| `MM/DD HH:mm` | 01/24 14:35 |
| `HH:mm` | 14:35 |
| `DD/MM hh:mm A` | 24/01 02:35 PM |
| `MM/DD hh:mm A` | 01/24 02:35 PM |
| `hh:mm A` | 02:35 PM |

---

### 〰️ Bounds

Both entity-level (`lower_bound`, `upper_bound`) and card-level axis options (`lower_bound`, `upper_bound` for primary; `lower_bound_secondary`, `upper_bound_secondary` for secondary) support three value types:

| Format | Behavior |
|--------|----------|
| `0` | **Hard bound** — axis edge is fixed at this value regardless of data |
| `"~0"` | **Soft bound** — axis prefers this value but expands if data exceeds it |
| `"sensor.entity_id"` | **Dynamic bound** — tracks the live state of another entity |

Card-level bounds set the baseline for the axis; entity-level bounds can further tighten or extend the range. When both are present, the most restrictive hard bound or the widest soft bound wins.

#### Y Axis Tick Control

Use `y_axis_ticks` to control how many divisions appear on the Y axis. The axis range is automatically snapped to clean round numbers so labels always look tidy.

```yaml
type: custom:statistics-graph-chart-card
lower_bound: 40
upper_bound: 100
y_axis_ticks: 6
entities:
  - entity: sensor.cpu_temperature
```

This produces labels at **40, 50, 60, 70, 80, 90, 100** — similar to setting `tickAmount: 6` in Apex Charts or an interval of 10 in Excel.

---

### ⚡ Auto Scale Points

When using the interval picker to switch between time ranges (1H → 7D → 90D), the default `points_per_hour` and `group_by` can be too dense for long periods or too sparse for short ones. Enable `auto_scale_points` to let the card pick a sensible bucket size automatically based on the visible window.

```yaml
type: custom:statistics-graph-chart-card
auto_scale_points: true
show_interval_picker: true
hours_to_show: 24
entities:
  - entity: sensor.power_consumption
  - entity: sensor.solar_production
  - entity: sensor.grid_export
```

The card chooses both bucket size and `group_by` from a fixed table, optimized to keep around 100 visible points at every zoom level:

| Visible window | Bucket | One point every |
|----------------|--------|-----------------|
| ≤ 4 hours | interval | 5 min |
| ≤ 12 hours | interval | 15 min |
| ≤ 36 hours | interval | 30 min |
| ≤ 4 days | hour | 1 hour |
| ≤ 10 days | interval | 2 hours |
| ≤ 100 days | date | 1 day |
| ≤ 1 year | week | 1 week |
| > 1 year | month | 1 month |

> **Note:** Entity-level `points_per_hour` overrides are not affected — only entities inheriting the card-level value are scaled.

**Safe fallback for advanced setups.** When any entity uses `offset`, `forecast_horizon`, or `data_attribute` (attribute-based forecast data), Auto-Scale steps aside and keeps your configured `points_per_hour` and `group_by` exactly as-is. These features create their own time windows that don't align with automatic re-bucketing, so the card stays out of the way to avoid breaking them.

---

### 📈 Rise/Fall Colors

Colors each graph segment based on its slope relative to the previous point. Unlike color thresholds (which react to absolute values), rise/fall coloring reacts to *direction of change* — making it easy to spot momentum shifts at a glance. The `trend_period_hours` setting on the entity controls the smoothing window used to determine whether a segment counts as rising, falling, or stable.

```yaml
rise_fall_colors:
  enabled: true
  increase: "#2ecc71"   # color when value is rising
  decrease: "#e74c3c"   # color when value is falling
  stable: "#95a5a6"     # color when value is flat
```

The same direction logic drives the trend icon (▲▼⯇⯈) on the state row — so the icon and the graph always agree.

> ⚠️ Cannot be combined with `color_thresholds` on the same entity.

---

### 🎨 Color Thresholds

```yaml
color_thresholds:
  enabled: true
  direction: vertical    # vertical or horizontal
  transition: smooth     # smooth or hard
  values:
    - value: 0           # at or above this value → use this color
      color: "#3498db"
    - value: 20
      color: "#2ecc71"
    - value: 35
      color: "#e74c3c"
```

Thresholds are sorted by value automatically. The color of the lowest threshold applies to everything below it.

Setting `color: threshold`, `state_color: threshold`, `icon_color: threshold`, or `point_colors: threshold` on the entity makes those elements also reflect the threshold color.

**`direction`** controls which axis the colors are painted along:
- `vertical` *(default)* — Y-axis gradient. Colors map to value height on the chart.
- `horizontal` — per-segment coloring along the time axis. Each segment gets the color of its data value.

**`transition`** controls how color changes between bands:
- `smooth` — gradual interpolation as values pass through thresholds
- `hard` — instant color switch exactly at the threshold value

> ⚠️ Cannot be combined with `rise_fall_colors` on the same entity.

---

### 👆 Tap Actions

| Action | Description |
|--------|-------------|
| `none` | No action *(default)* |
| `more-info` | Open entity detail dialog |
| `navigate` | Navigate to a dashboard path (requires `navigation_path`) |
| `url` | Open an external URL (requires `url`) |
| `call-service` | Call an HA service (requires `service` and optional `service_data`) |

---

### 🔣 State Map

Maps non-numeric state strings to integer values for graphing. Order determines the number (0-based index). The Y-axis automatically shows the original state names (or optional `label`) instead of the numeric index.

```yaml
state_map:
  - value: "off"             # → 0, axis shows "off"
  - value: "idle"            # → 1, axis shows "idle"
  - value: "on"              # → 2, axis shows "on"
```

With optional friendly labels:

```yaml
state_map:
  - value: "off"
    label: Stopped           # axis shows "Stopped"
  - value: "on"
    label: Running           # axis shows "Running"
```

The state row always displays the original string (or label if provided), not the number.

> ⚠️ State values are case-sensitive and must match exactly what HA reports (always lowercase for `binary_sensor`).
> Auto-detected for `binary_sensor`, `input_boolean`, and `input_select` entities — no `state_map` needed in step mode.

</details>

---

## 🛠️ Visual Editor

<details>
<summary>Editor tabs, drag-and-drop, dynamic behavior</summary>

The card ships with a full visual editor — no YAML required. Every option in this documentation is reachable from the Lovelace UI. Changes apply immediately without a page reload.


### General Settings — Four Tabs

The General Settings panel is divided into four tabs to reduce clutter:

| Tab | Contents |
|-----|----------|
| **Display** | Chart mode, height, header, icon, graph data (hours, points/hour, group by, update interval, visible window, scroll mode), visual toggles (grid, tooltip, stacked, sparkline, auto scale, compact legend + position…), battery |
| **Y Axis** | Visibility (Y-axis, Y2-axis, Y ticks, axis labels toggle, logarithmic), labels (custom axis label text, ticks, decimals, font size, opacity), bounds (min range, lower/upper bounds) |
| **X Axis** | Visibility (X-axis, X ticks), labels (date format, bar spacing, font size, opacity, X axis interval), time window (graph start hour, show full period) |
| **Overlay** | Interval Picker, Attribute List, Tooltip Sync, Energy Date Sync, Date Picker (position + group + visible modes), Annotations |

Settings that depend on a toggle are automatically dimmed when the parent is off — for example, Sync Group is disabled when Tooltip Sync is off, and Interval Position is disabled when Interval Picker is off.

### Entity Configuration — Four Tabs

Each entity panel has four tabs:

| Tab | Contents |
|-----|----------|
| **General** | Entity picker, statistic ID, custom name, custom unit, tap action |
| **Data** | Y axis, aggregation, attribute, decimals, points/hour, offset, value factor, number format, value transform, fixed value, invert, attribute data source, state map |
| **Appearance** | Graph toggle, graph type, extrema, average, range band, stack group, line, fill, data points, state row (on / gauge / off), trend icon, Y axis range, legend |
| **Colors** | Base colors (line, icon, state), rise/fall colors, color thresholds with transition mode |

Entity options also adapt dynamically based on Chart Mode — see [Dynamic Editor Behavior](#-dynamic-editor-behavior).

### Drag and Drop

Entities can be reordered by dragging the grip handle (⠿) on the left side of each entity row. The order determines drawing order on the graph and row order in the state display.

### Info Tooltips

Every configuration field has an info tooltip (ⓘ) with a detailed explanation. Hover or tap the icon next to any label to learn what the option does, see practical examples, and understand how it interacts with other settings.

---

---

### 🔄 Dynamic Editor Behavior

The visual editor adapts in real time based on the current configuration. Options that don't apply are completely removed from the UI — not just disabled, but hidden. This keeps the editor clean regardless of which chart mode or feature combination you choose.

### Chart Mode → General Settings

Changing the Chart Mode dropdown instantly reconfigures the entire editor. The card-level settings are organized into six tabs (**Chart**, **Card**, **Overlay**, **X Axis**, **Y Axis**, **Calendar**) — irrelevant tabs disappear entirely based on the chart mode.

| When Chart Mode is… | Visible tabs | What's hidden inside |
|---|---|---|
| **Timeline** | All six tabs | Nothing — full editor |
| **Scatter** | Chart, Card, Overlay, X Axis, Y Axis | Calendar tab gone. Stacked / Sparkline / Animate / Logarithmic hidden in Chart. Bar Spacing hidden in Chart. |
| **Pie / Ranking / Radar / Polar Area / Radial Bar** | Chart, Card, Overlay, (X Axis only for Pie/Ranking/Radar) | Y Axis and Calendar tabs gone. Most Chart options hidden — only mode-relevant ones remain. Overlay shows only Interval Picker and Attribute List. |
| **Heatmap / Calendar** | Chart, Card, Overlay, X Axis, Calendar | Y Axis tab gone. Bar / line settings hidden. |
| **State Timeline** | Chart, Card, Overlay, Calendar | Axis tabs gone — state timelines don't have Y values. |
| **Sparkline mode** | Chart, Card | Everything else gone — sparkline is chrome-free. |

### Chart Mode → Entity Settings

Each entity's expanded settings are organized into six tabs in a 3×2 grid: **General**, **Graph**, **Basic** / **State Row**, **Colors**, **Advanced**. Switching the chart mode reshapes the visible options. Fields that have no effect in the current mode are completely hidden — Pie charts don't show Point Color or Color Thresholds, and Heatmap hides Rise/Fall Colors.

**Graph tab**

| When Chart Mode is… | What's visible |
|---|---|
| **Timeline** | Graph Type (line / step / bar), Show Extrema, Show Average, Range Band, Break on Gaps, Line block (with width & Bezier), Fill block (with gradient), Data Points, Y Axis Range |
| **Scatter** | Show Extrema, Data Points, Y Axis Range (no Graph Type, no Line/Fill, no Average) |
| **Radar** | Line, Fill, Data Points (no Graph Type, no Extrema/Average) |
| **All other modes** (Pie, Ranking, Radial Bar, Polar Area, Heatmap, Calendar) | Only Y Axis Range remains |

**State Row tab**

Available in all chart modes. Shows the State Row block (primary/secondary value, name position, MDI icon, font sizes, adaptive color) and the Trend Icon block.

**Basic tab**

| Field | Visible in… |
|---|---|
| **Y Axis** (Primary / Secondary / Independent) | Timeline, Scatter |
| Aggregate Function, Attribute, Points/Hour, Decimals, Number Format | All modes (universal) |
| **Legend** (per-entity stats: Min, Avg, Max, Last, Sum) | All modes |

**Advanced tab**

Available in all chart modes. Always shows: Forecast Horizon, Offset, Value Factor, Value Transform, Fixed Value, State Map, Attribute Data Source.

| Field | Visible in… |
|---|---|
| **Invert (Mirror)** | Timeline only |

**Colors tab**

| Field | Visible in… |
|---|---|
| Line / Fill Color | All modes (universal). Accepts `{{ }}` Jinja2 templates |
| Icon Color, State Color | All modes. Accepts `{{ }}` templates |
| **Point Color** | Timeline, Scatter, Radar |
| **Rise/Fall Colors** | Timeline only |
| **Color Thresholds** | All modes **except** Pie and Polar Area (single color is meaningful for slices) |


### Sparkline → Entire Card

When `sparkline` is enabled (Timeline mode only):

- **Card tab**: Header and Icon sections disappear; only Card Styling remains
- **Overlay tab**: Hidden entirely — overlays don't render in sparkline mode
- **X Axis / Y Axis / Calendar tabs**: Hidden entirely
- The card renders with zero chrome — no toolbar, axes, grid, or legend

### Entity-Level Cascading

Within each entity, toggle states cascade downward — disabling a parent hides or disables all its children:

| When this is… | These become hidden / disabled |
|---|---|
| `show_graph: off` | Graph Type, Extrema, Average, Line, Fill, Points — all hidden |
| `show_line: off` | Line Width, Bezier — disabled |
| `show_fill: off` | Gradient — disabled |
| `show_state: off` | Show Last, Adaptive Color, Icon, Align, all Size fields — disabled |
| `show_state: gauge` | Same fields disabled (gauge draws its own layout from `lower_bound` / `upper_bound`) |
| `show_trend_icon: off` | Trend Period, Trend Icon Size — disabled |

### Entity Count Limits

The "Add Entity" button automatically hides when the chart mode's limit is reached:

| Chart Mode | Max Entities | Notes |
|---|---|---|
| Timeline | Unlimited | Mix line, step, bar freely |
| Scatter | 2 | Entities labeled **X** and **Y** in the editor |
| Pie / Ranking | Unlimited | Each entity = one slice / bar |
| Radial Bar | Unlimited | Each entity = one concentric ring |
| Polar Area | Unlimited | Each entity = one equal-angle slice |
| Radar | 3+ minimum | Each entity = one spoke of the polygon |
| Heatmap / Calendar | 1 | Only the first entity is used |

### Option Interactions

Some options depend on or conflict with each other:

| If you set… | Then… |
|---|---|
| `value_transform` set | Runs after `value_factor`. Available variables: `x`, `first`, `last`, `min`, `max`, `avg`, `index`. State row shows the transformed value |
| `offset` set (per entity) | Data is fetched from a shifted time window but displayed aligned with the current window. Same entity with different offsets = period comparison at full graph quality |
| `stacked: true` | Only affects entities with the same `y_axis` and `graph_type` |
| `auto_scale_points: true` | Only scales entities that inherit the card-level `points_per_hour` — entity-level overrides are not affected |
| `color_thresholds` enabled | Cannot combine with `rise_fall_colors` on the same entity |
| `show_state: gauge` | Uses entity `lower_bound` / `upper_bound` as gauge min/max; falls back to stats if not set |
| `chart_mode: heatmap` + `color_thresholds` | Heatmap cells use threshold colors instead of single-color opacity gradient |
| `sparkline: true` | Only works in Timeline mode; ignored in other chart modes |
| `max_visible_interval` set | Enables scroll; `scroll_mode` controls whether scrollbar is visible or mouse-wheel only |
| `show_y_axis: false` | Hides primary (left) axis labels; secondary axis is not affected |
| `show_y2_axis: false` | Hides secondary (right) axis labels; primary axis is not affected. Right padding shrinks. |
| `show_legend: true` | Compact Legend appears below graph. Combine with `show_state: false` on entities for maximum graph space |
| `legend_stats` | Only takes effect when entity `show_in_legend` is `true`. Any combination of `min`, `avg`, `max`, `last` |
| `align_state: bottom-*` | State row renders below the graph instead of above. Can be mixed — some entities top, some bottom |
| `show_range_band: true` | Only visible in Timeline mode with line/step entities. Band is drawn behind the normal line and fill. Tooltip adds a min → max row |
| `chart_mode: radialbar` | Uses `lower_bound` / `upper_bound` per entity to define the 0–100% ring fill. Falls back to stats min/max if not set |
| `chart_mode: radar` | Requires at least 3 entities. Uses `lower_bound` / `upper_bound` per entity for normalization |
| `energy_date_sync: true` | Card time range follows the Energy dashboard date picker. When viewing today, X axis ends at the current time and live updates continue. When viewing a past date, live updates are paused. Overrides `hours_to_show` while active |
| `statistic_id` set (with empty `entity`) | Data is fetched from the statistics database only — no History API call. State row shows last statistics value. WebSocket live updates are skipped for this entity |
| `color: "{{ ... }}"` | Template is evaluated server-side via `render_template` WS subscription. Push-based — no polling. Editor color picker dims automatically. Falls back to the raw template string if resolution fails |
| `graph_start: tomorrow` | Window is tomorrow 00:00 → end of day. `show_full_period` is not required. History fetch is skipped (no past data in tomorrow's range). Ideal with `data_attribute` for forecast/spot price data |
| `y_grid_style` / `x_grid_style` | Only effective when `show_grid: true`. Applies inline SVG styles that override the default CSS class |
| `decimals` on pie/radial entity | Controls both value precision *and* percentage precision in slice labels, tooltips, and center totals |

</details>

---

## 📄 License

MIT

<a href="https://www.buymeacoffee.com/cataseven" target="_blank">
  <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me a Coffee" style="height: 60px !important;width: 217px !important;" >
</a>


[![Star History Chart](https://api.star-history.com/svg?repos=cataseven/Statistics-Graph-Chart-Card&type=date&legend=top-left)](https://www.star-history.com/#cataseven/Statistics-Graph-Chart-Card&type=date&legend=top-left)
