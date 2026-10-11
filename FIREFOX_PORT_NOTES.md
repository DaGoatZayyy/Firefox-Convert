# Purpura Firefox port

## Changes
- Replaced Chromium's MV3 `background.service_worker` with Firefox's `background.scripts`.
- Loads `scripts/js/trading.js` before `scripts/background.js`, preserving the original import order.
- Guards the service-worker-only `importScripts()` call so it does not run in Firefox's background page.
- Adds Gecko extension ID and minimum-version metadata.
- Removes Chromium-only `minimum_chrome_version`.

## Test locally
1. Extract the full `purpura_firefox_port.zip` archive.
2. Open `about:debugging#/runtime/this-firefox`.
3. Click **Load Temporary Add-on…** and select the extracted `manifest.json`.
4. Test the features on Roblox. Inspect both the extension background console and the Roblox page console if a button fails.

## Status
All 18 JavaScript files passed Node syntax checks and the manifest JSON parsed successfully. This is not yet a live Firefox/Roblox functional test; network permissions and APIs can still differ from Chromium. The full source archive contains the assets and files needed to run the extension; this GitHub repository currently contains the Firefox manifest and these notes, not the entire archive.
