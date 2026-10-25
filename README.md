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

Firefox (Release) only installs signed add-ons, so the add-on has to be signed by Mozilla. It's free and the add-on stays private:

1. Go to [addons.mozilla.org/developers](https://addons.mozilla.org/developers/) and sign in with a Firefox account.
2. Click **Submit a New Add-on**.
3. Choose **On your own** (unlisted), so it is not published.
4. Upload `firefox-newtab.zip`. Automatic signing usually takes a few minutes.
5. Download the signed `.xpi`.
6. In Firefox open `about:addons`, click the gear icon, then **Install Add-on From File...** and select the `.xpi`.

If AMO rejects the add-on ID, change `browser_specific_settings.gecko.id` in `manifest.json` to your own (e.g. `newtab@yourname.dev`) and upload again.

### Unsigned install (Developer Edition, Nightly, ESR)

These builds allow unsigned add-ons: set `xpinstall.signatures.required` to `false` in `about:config`, then install the `.zip` from `about:addons`. This preference is ignored on Firefox Release.

## Changes from the Chromium version

- `manifest.json`: added `browser_specific_settings.gecko` (required by Firefox, min version 117), removed `$schema`.
- `script.js`: searches use `browser.search.search()` on Firefox (and `chrome.search.query()` on Chromium), so the browser's default search engine is respected. If neither API is available it falls back to DuckDuckGo.

## Credits

- Original extension by [diggingforce](https://github.com/diggingforce/chromium-newtab) (MIT)
- Settings menu by [zyqunix](https://github.com/zyqunix)
- [Departure Mono](https://departuremono.com/) by Helena Zhang (SIL OFL 1.1)
- [Maple Mono](https://github.com/subframe7536/maple-font) by subframe7536 (SIL OFL 1.1)
