# Folio Themes

Downloadable UI themes for [Folio Reader](https://github.com/folio-etc/folio),
distributed as `.cptheme` archives.

## Layout

```
themes/<id>/theme.yml    # one source directory per theme
```

A `.cptheme` is a ZIP (STORED) holding the converted `theme.json` plus any
bundled `.cpfont` files. Build them with the firmware repo's
`scripts/build_cptheme.py`:

```sh
python3 ../folio/scripts/build_cptheme.py themes/classic -o dist/classic.cptheme
```

## Releases

The [Build & Publish SD Card Themes](.github/workflows/release-themes.yml)
workflow (`workflow_dispatch`) builds every theme, generates `themes.json`, and
publishes them as Release assets. The device downloads from the stable
`sd-themes-m<manifest>-b<cpfont>` tag.

Requires a `THEMES_REPO_TOKEN` secret: a fine-grained PAT with `contents:read`
on the firmware repo (the build engine is checked out from there) and
`contents:write` on this repo.

## Installing manually

Copy a theme folder's `.cptheme` to `/.themes/` (or `/themes/`) on the SD card,
or use **Settings > Display > Download Themes** on the device.
