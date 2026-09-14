# NAVY — Unraid webGUI theme

Modern dark navy with cyan accents, no animation

![NAVY dashboard](screenshot.jpg)

## What it looks like
The calm one. Same layered dark-navy surfaces and rounded dashboard cards, cyan links and
accents, gradient usage bars — but no orbiting rings or moving rails. Lighter on the GPU and a
good pick for always-on wall displays or low-power clients.

Shared with every theme in this repo: page gutters that stay visible instead of collapsing on
narrow windows, wide tables that scroll inside their own box (so the page never slides sideways),
and a mobile pass covering the banner, panels, device tables, Community Applications layout and
form controls.

## Install

**Plugins tab (recommended)** — *Plugins → Install Plugin*, paste:
```
https://raw.githubusercontent.com/GaBoNtZ/unraid-themes/main/navy/navy-theme.plg
```
**By hand** — copy `navy-theme.plg` to `/boot/config/plugins/` on the server, then:
```
installplg /boot/config/plugins/navy-theme.plg
```
Afterwards pick the **Black** theme in *Settings → Display Settings* and hard-refresh (Ctrl+F5).

The plugin writes the stylesheet to flash, backs up the stock `themes/black.css`, and copies itself
into place. Unraid reinstalls plugins on every boot, so it survives reboots on its own.

## Uninstall
*Plugins → Remove*. The stock Black theme is restored from the backup, the flash folder is deleted.
Hard-refresh afterwards.

## Gotchas
- **It replaces the Black theme file.** All three themes in this repo share
  `themes/black.css`, so **only install one at a time** — the last one installed wins.
- **Hard-refresh after installing** (Ctrl+F5). Browsers cache the stylesheet aggressively, and
  phones especially will keep showing the old look until their cache is cleared.
- **The banner is not part of the theme.** Artwork comes from *Settings → Display Settings*
  (`/boot/config/plugins/dynamix/banner.png`). Screenshots here show a custom banner.
- **Built against Unraid 7.2.4** (`min="7.0.0"`). Lime Tech moves selectors between releases —
  after a major OS upgrade, check the look before assuming it still fits. The installer refuses to
  re-backup a stock file it no longer recognises, so your rescue copy stays intact.
- **Device tables reflow on phones.** Stock Unraid pins them to 1000px with no mobile override, so
  a phone only ever sees the left slice. These themes let them fit the screen instead — a
  deliberate deviation from stock.
- **If you previously pinned a theme via the `go` file, remove that block** — the plugin owns
  persistence now and the two would fight over the same file.
- No animation at all, so nothing to disable for reduced-motion users.
- Slightly brighter accent (`#29a8ff`) than Reforged; pairs well with Unraid's stock orange branding.

## Files
| File | Purpose |
|---|---|
| `navy-theme.plg` | The plugin. Stylesheet embedded inline — installs offline, no downloads. |
| `source/black.css` | The stylesheet on its own, if you would rather drop it in by hand. |
| `screenshot.jpg` | The theme running on a live 7.2.4 server. |
| `banner.png` | The banner artwork used in the screenshot (optional, see below). |

CSS only — no scripts, no PHP, no page templates, no containers, no services.

## Matching banner (optional)

The artwork in the screenshots is **not** part of the theme — Unraid keeps it separate. The banner
used here ships alongside as `banner.png`:

```
scp banner.png root@tower:/boot/config/plugins/dynamix/banner.png
```
Then *Settings → Display Settings* → set **Banner** to the custom image. The plugin never touches
your banner, so installing or removing a theme leaves your own artwork alone.
