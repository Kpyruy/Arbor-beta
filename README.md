# Arbor beta builds

Testing-only distribution of [Arbor](https://github.com/Kpyruy/Arbor). This repository is **not** a second plugin or a Community Plugins release.

Current test build: **0.3.1-beta.1**, from [source commit 38dcf4e](https://github.com/Kpyruy/Arbor/commit/38dcf4e32e49a66a14501a609deb1a1e883d2ea7).

## Install on iPad with BRAT

1. Save any open Arbor edits. Disable Arbor in **Settings → Community plugins**, but **do not uninstall it**.
2. Install and enable **BRAT** from Community plugins if you do not have it yet.
3. Open **BRAT settings → Add beta plugin** and enter `Kpyruy/Arbor-beta` (or this repository's URL).
4. If BRAT shows a version selector, choose **0.3.1-beta.1**. Add/install the plugin.
5. Re-enable Arbor in Community plugins. If Obsidian still shows the old build, fully close and reopen the app. Check that Arbor's version is **0.3.1-beta.1**.

This build keeps the plugin ID `arbor`. BRAT replaces only the plugin's program files; it does not require access to the hidden `.obsidian` folder and does not replace `data.json` or your notes. Keep your normal vault backup. Do not uninstall the existing plugin just to try this build.

While testing, do not update Arbor from Community plugins: that may restore the stable build. You do not need a GitHub token for this public repository.

## Quick test

- **Header:** check that `Full tree` and zoom no longer overlap.
- **Drag targets:** in split view, drag an excerpt onto an Arbor card, then move from the card across the gap to **New block beside** or **New child block**. The targets should stay reachable inside Arbor.
- **Result:** dropping on either target should create exactly one block in the intended place, preserve the source reference, and leave the original card unchanged. Try one drop with the floating keyboard visible if possible.

Moving completely outside the Arbor pane should clear the targets. Report feedback in [Arbor issue #7](https://github.com/Kpyruy/Arbor/issues/7).

## Returning to stable

Remove this repository from BRAT's beta-update list **without uninstalling Arbor**. Once the stable fix is released in the main repository, update Arbor normally through Community plugins. Until then, you can keep this beta or reinstall the stable program files while preserving `data.json`.

## Build identity

`main.js` and `styles.css` are byte-for-byte the tested candidate from the source commit above; only the distribution manifest's version is changed. The source candidate passed **1154 automated tests**, lint/build checks, and desktop browser header checks. Actual iPad drag acceptance is still pending.

Release assets are `main.js`, `styles.css`, and `manifest.json`. Root copies are provided for compatibility; `manifest-beta.json` points to the same beta version for older BRAT clients. Source development and stable releases remain in the main repository. License: MIT.
