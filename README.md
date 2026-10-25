# firefox-newtab

a custom minimal new tab extension for Firefox / LibreWolf.

Firefox port of [diggingforce/chromium-newtab](https://github.com/diggingforce/chromium-newtab).

- Fully customizable
- Bangs support

## How to use

### Temporary install (any Firefox-based browser)

1. Clone or download this repository and extract it.
2. Open `about:debugging#/runtime/this-firefox`.
3. Click **Load Temporary Add-on...** and select `manifest.json` (or the `.zip`).
4. Open a new tab and enjoy.

The add-on is removed when the browser restarts.

### Permanent install on LibreWolf

1. Open `about:config` and set `xpinstall.signatures.required` to `false`.
2. Open `about:addons`, click the gear icon, then **Install Add-on From File...** and select the `.zip`.

### Permanent install on regular Firefox

Firefox only installs signed add-ons. Upload the `.zip` as an **unlisted** add-on on [addons.mozilla.org](https://addons.mozilla.org/developers/), download the signed `.xpi`, then install it from `about:addons`.

## Changes from the Chromium version

- `manifest.json`: added `browser_specific_settings.gecko` (required by Firefox, min version 117), removed `$schema`.
- `script.js`: searches use `browser.search.search()` on Firefox (and `chrome.search.query()` on Chromium), so the browser's default search engine is respected. If neither API is available it falls back to DuckDuckGo.

## Credits

- Original extension by [diggingforce](https://github.com/diggingforce/chromium-newtab) (MIT)
- Settings menu by [zyqunix](https://github.com/zyqunix)
- [Departure Mono](https://departuremono.com/) by Helena Zhang (SIL OFL 1.1)
- [Maple Mono](https://github.com/subframe7536/maple-font) by subframe7536 (SIL OFL 1.1)
