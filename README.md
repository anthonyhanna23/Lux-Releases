# Lux — releases

**Lux** is a RAW photo editor for macOS and Windows: a Lightroom-style Develop
module plus a layer-based Studio, with all processing done on your own machine.

This repository exists **only to host release downloads**. It contains no source
code — Lux is closed-source commercial software.

## This is a private beta

Downloads here require a **license code** — something like
`LUX-4K7M-9PQR-2XVB` — and codes are issued individually. If you have not been
given one, the app will not open. Codes are not for sale yet and are not
transferable.

If you were invited: grab the newest installer from
[Releases](../../releases/latest) and type your code when the app first
launches. Your code works on two computers, and Lux needs to be online just for
that first moment on each one — after that it runs entirely offline. If you
change computers, the app lists the ones you are using and lets you release one.

Activating sends your code, an anonymous ID for the computer, its name, platform
and the app version — enough to count computers, nothing more. Your photos and
edits never leave your machine.

## Installing on macOS

These builds are **not notarized by Apple yet**, so macOS will refuse to open
the app on first launch. To get past it:

```sh
xattr -dr com.apple.quarantine /Applications/Lux.app
```

Or right-click the app and choose *Open* — on recent macOS you may also need
*System Settings -> Privacy & Security -> Open Anyway*.

This will stop being necessary once the app is signed and notarized.

## Getting started

**1. Import.** Drag photos onto the window, or use the **Import** button. RAW
files (CR2, ARW, RAF, DNG, NEF, CR3, ORF, RW2, PEF, SRW and anything else LibRaw
reads) plus JPEG, PNG and WebP.

Importing does **not** copy your files. Lux records where each one lives and
reads it from there, so importing 500 GB of RAWs does not consume another 500 GB.

**2. Sort in Library.** Grid and Loupe views, star ratings (`0`–`5`),
pick/reject flags (`P` / `X`), color labels (`6`–`9`), collections, and
filtering by any of those. Right-click any photo for the same actions.

**3. Edit in Develop.** Select a photo and press `D`. Everything is
non-destructive — your original file is never modified, and every edit lives in
the catalog and can be undone or reset at any time.

**4. Export.** JPEG or PNG, with quality and size controls. Choose the
destination folder first, then export. Select several photos with `⌘` or
`⇧` in the Library and they are all written out in one go.

## The three tabs

**Library** — browsing, rating, organizing, searching.

**Develop** — the Lightroom-style adjustments:

- **Basic** — white balance, exposure, contrast, highlights, shadows, whites,
  blacks, texture, clarity, dehaze, vibrance, saturation, color or B&W
- **Tone Curve** — RGB master plus per-channel curves
- **Color Mixer** — hue, saturation and luminance for eight color bands
- **Color Grading** — shadow / midtone / highlight wheels
- **Detail** — sharpening: amount, radius, detail and masking
- **Noise Reduction** — separate Color and Luminance controls, with Preserve
  Detail to protect texture
- **Effects** — vignette, film grain, defocus
- **Lens Corrections** — distortion, chromatic aberration, defringe, vignetting
- **Masking** — AI Subject and Background selection, Sky, Brush, Linear Gradient and
  Radial Gradient, Luminance Range and Color Range. Every mask carries its own
  full set of adjustments.

Hold `\` at any time to see the before/after.

**Studio** — Photoshop-style layers stacked on top of your Develop edits: raster
layers, 23 blend modes, layer masks, selections (marquee, lasso, magic wand,
Select Subject), brush and eraser, editable shapes, guides and snapping.

## Things that work differently to Lightroom

**Your originals are linked, not copied.** Lux never moves or modifies them. The
catch: if you move or rename the folder your photos live in, Lux marks them as
missing until you relink. Your edits survive that — they are in the catalog, not
in the file.

**Studio's bottom layer stays live.** Where Lightroom hands off to Photoshop by
rendering a TIFF and freezing your RAW edits into it, Studio's base layer is a
live reference to your Develop settings. Change exposure in Develop, flip back to
Studio, and it has already updated. You can go back and forth as often as you
like without losing anything, and there are no extra files to manage.

**Virtual copies cost nothing.** Right-click a photo → *Create Virtual Edit Copy*
for a second independent set of edits on the same original. It duplicates zero
pixels, so a dozen treatments of one RAW cost a dozen rows of metadata.

**Resolution arrives on demand.** Editing runs on a fast downscaled proxy. The
moment a crop or zoom means the screen is showing more detail than the proxy
holds, the original is re-decoded at the resolution the view needs and swapped
in. If a zoomed view looks soft for a second, that is what is happening.

**AI masking downloads a model once.** The first time you use Subject or
Background masking, Lux asks permission to download the segmentation model
(~176 MB) and then caches it in your catalog. It runs on your own machine —
nothing about your photos is uploaded, ever.

Your catalog lives in `~/Documents/Lux`.

## Keyboard shortcuts

### Library and Develop

| Key | Action |
| --- | --- |
| `G` / `E` / `D` | Grid · Loupe · Develop |
| `←` `→` | Previous / next photo |
| `0`–`5` | Star rating |
| `P` / `X` / `U` | Pick / Reject / Unflag |
| `6`–`9` | Color label (red, yellow, green, blue) |
| `R` | Crop tool |
| `O` | Toggle mask overlay |
| `Z` | Toggle fit / 100% zoom |
| `+` / `-` | Zoom in / out a stop |
| `⌘+` / `⌘-` | Zoom in / out a stop |
| `⌘[` / `⌘]` | Rotate 90° left / right |
| `\` | Before / after (hold) |
| `Enter` | Finish cropping |
| `Esc` | Leave crop, deselect mask, or zoom to fit |
| `⌘Z` / `⇧⌘Z` | Undo / redo |
| `⇧⌘C` / `⇧⌘V` | Copy / paste Develop settings |
| `⌘A` | Select all photos |
| `Delete` | Remove selected from the catalog (asks first) |

Removing a photo only clears it from Lux's catalog. Your file on disk is never
deleted.

### Studio

| Key | Tool |
| --- | --- |
| `V` / `T` | Move · Transform |
| `M` / `Q` / `W` | Marquee · Lasso · Magic Wand |
| `U` / `E` / `L` | Rectangle · Ellipse · Line |
| `B` / `X` | Brush · Eraser |

| Key | Action |
| --- | --- |
| `⌘A` / `⌘D` | Select all / deselect |
| `⇧⌘I` | Invert selection |
| `⌘J` / `⇧⌘J` | New layer from selection (copy / cut) |
| `⌘;` | Show or hide guides |
| `⌘Z` / `⇧⌘Z` | Undo / redo |

While making a selection, hold `⇧` to add and `⌥` to subtract.

## Updates

Lux checks for new versions on its own and tells you when one is out. It never
downloads or installs anything without asking.

On Windows, choose **Download** and Lux fetches the update, then asks whether to
restart into it now or install it the next time you quit. On macOS it cannot
install updates for you yet (that needs code signing), so **Open download** brings
you back here for the new version; drag it into Applications and choose Replace.

## Reporting problems

Please open an [issue](../../issues) — include what you were doing, your macOS or
Windows version, and the camera the file came from if it is RAW-related.

Being a beta, it is worth saying plainly: **keep your own backups of work you
care about.** Lux is designed not to touch your originals, but this is
pre-release software running over your photo library.

## Licensing

Lux itself is proprietary; see [LICENSE](LICENSE). Third-party components and
their licenses are listed in
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).
