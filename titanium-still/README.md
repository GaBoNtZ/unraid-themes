# TITANIUM STILL — Unraid webGUI theme

Everything TITANIUM looks like, with nothing moving.

![TITANIUM STILL](screenshot.png)

## What it looks like
Identical to [TITANIUM](../titanium/): layered navy panels, cyan rails along the header and section
titles, ring-framed dashboard cards, gradient usage bars. The difference is that every Pulse
animation is **paused** — the rails and rings are still drawn, they simply do not travel.

It is built from TITANIUM's own `--titanium-pulse-play-state` token, the hook its author left for a
motion-off build, so the two stay pixel-identical apart from motion.

Pick this one for wall displays, low-power or remote clients (VNC/RDP, a Pi dashboard), or if you
simply find moving UI distracting.

## Install

**Plugins tab (recommended)** — *Plugins → Install Plugin*, paste:
```
https://raw.githubusercontent.com/GaBoNtZ/unraid-themes/main/titanium-still/titanium-still-theme.plg
```
**By hand** — copy `titanium-still-theme.plg` to `/boot/config/plugins/` then:
```
installplg /boot/config/plugins/titanium-still-theme.plg
```
Then pick the **Black** theme in *Settings → Display Settings* and hard-refresh (Ctrl+F5).

## Uninstall
*Plugins → Remove* — the stock Black theme is restored from the copy shipped inside the plugin.

## Gotchas
- **Only install one theme from this repo at a time.** They all write to `themes/black.css`.
- TITANIUM and TITANIUM STILL are mutually exclusive — installing one replaces the other.
- Hard-refresh after installing; browsers and phones cache the stylesheet hard.
- Built against **Unraid 7.2.4** (`min="7.0.0"`); re-check after a major OS upgrade.
- If you only want motion off *temporarily*, you do not need this build: your OS-level
  **reduce motion** setting already pauses TITANIUM's animations (on iOS, Low Power Mode does too).

## Files
| File | Purpose |
|---|---|
| `titanium-still-theme.plg` | The plugin, stylesheet embedded inline. |
| `source/black.css` | The stylesheet on its own. |
| `screenshot.png` | Still capture (2560×1440). |
| `banner.png` | The banner artwork used in the capture (optional, see below). |

CSS only — no scripts, no PHP, no page templates, no containers, no services.

## Matching banner (optional)

The artwork in the screenshots is **not** part of the theme — Unraid keeps it separate. The banner
used here ships alongside as `banner.png`:

```
scp banner.png root@tower:/boot/config/plugins/dynamix/banner.png
```
Then *Settings → Display Settings* → set **Banner** to the custom image. The plugin never touches
your banner, so installing or removing a theme leaves your own artwork alone.
