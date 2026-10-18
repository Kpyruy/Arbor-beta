# Arbor beta builds

Testing-only distribution of [Arbor](https://github.com/Kpyruy/Arbor). This repository is **not** a second plugin or a Community Plugins release.

Current test build: **[0.3.1-beta.2](https://github.com/Kpyruy/Arbor-beta/releases/tag/0.3.1-beta.2)** — iPad keyboard layout, pinch zoom and compact drop targets.

Already using this repository in BRAT? Check for beta plugin updates. If your version is pinned to beta.1, change the selected version to **0.3.1-beta.2**. Restart Obsidian and check the installed Arbor version; no uninstall or manual file replacement is needed.

## Install on iPad with BRAT

1. Save any open Arbor edits. Disable Arbor in **Settings → Community plugins**, but **do not uninstall it**.
2. Install and enable **BRAT** from Community plugins if you do not have it yet.
3. Open **BRAT settings → Add beta plugin** and enter `Kpyruy/Arbor-beta` (or this repository's URL).
4. If BRAT shows a version selector, choose **0.3.1-beta.2**. Add/install the plugin.
5. Re-enable Arbor in Community plugins. If Obsidian still shows the old build, fully close and reopen the app. Check that Arbor's version is **0.3.1-beta.2**.

This build keeps the plugin ID `arbor`. BRAT replaces only the plugin's program files; it does not require access to the hidden `.obsidian` folder and does not replace `data.json` or your notes. Keep your normal vault backup. Do not uninstall the existing plugin just to try this build.

While testing, do not update Arbor from Community plugins: that may restore the stable build. You do not need a GitHub token for this public repository.

## Quick test

- **Keyboard:** in both Branch Editor and Tree Overview, switch between the full keyboard, floating keyboard and hidden keyboard. The bottom buttons should return to their normal position without reloading.
- **Pinch:** in Branch Editor, slowly zoom in and out on a short and a long card, then reverse direction and release. Try scrolling with one finger before adding the second finger. Watch for jumps or a sudden recenter when releasing.
- **Drag targets:** with the keyboard visible in split view, drag an excerpt onto a card, then across the gap to **New block beside** or **New child block**. The independent targets should remain reachable without covering the bottom buttons; in tight spaces they can sit side by side.
- **Result and regression:** each drop should create one block, preserve the source reference and leave the original unchanged. Check that Tree Overview navigation still feels good and switching views keeps the zoom.

Moving completely outside the Arbor pane should clear the targets. Report feedback in [Arbor issue #7](https://github.com/Kpyruy/Arbor/issues/7).

## Returning to stable

Remove this repository from BRAT's beta-update list **without uninstalling Arbor**. Once the stable fix is released in the main repository, update Arbor normally through Community plugins. Until then, you can keep this beta or reinstall the stable program files while preserving `data.json`.

## Build identity

Source baseline: [38dcf4e](https://github.com/Kpyruy/Arbor/commit/38dcf4e32e49a66a14501a609deb1a1e883d2ea7), plus the unreleased keyboard/pinch/drop-layout fixes in this candidate. Those follow-up source changes are not yet committed upstream; the baseline link alone does not contain them. This repository's tagged distribution records the exact tested program files; the distribution manifest changes the version only.

The candidate passed **1171 automated tests**, scoped lint/build and clean-source lint/build checks, **48 browser geometry configurations**, and a **30-second gesture stress check**. Browser checks do not replace a real iPad test; keyboard and pinch feedback is still needed. Previous beta.1 feedback confirmed the earlier drag-and-drop fix.

SHA-256 of the tested program files:

```text
main.js     4073a0a6a0d4be3acc79e76bf8da0589c7a14b6538491b8b5b3636fa0788cecf
styles.css  0dc7f1ee343a9489a0b55dfea881788605cfee0d3a3bfa77a8976a74af492603
```

Release assets are `main.js`, `styles.css`, and `manifest.json`. Root copies are provided for compatibility; `manifest-beta.json` points to the same beta version for older BRAT clients. Source development and stable releases remain in the main repository. License: MIT.
