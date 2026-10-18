# Arbor beta builds

Testing-only distribution of [Arbor](https://github.com/Kpyruy/Arbor). This repository is **not** a second plugin or a Community Plugins release.

Current test build: **[0.3.1-beta.3](https://github.com/Kpyruy/Arbor-beta/releases/tag/0.3.1-beta.3)** — natural vertical scrolling in touch Branch Editor columns, retaining the keyboard, pinch zoom and drop-target fixes.

Already using this repository in BRAT? Check for beta plugin updates. If your version is pinned to an older beta, change the selected version to **0.3.1-beta.3**. Restart Obsidian and check the installed Arbor version; no uninstall or manual file replacement is needed.

## Install on iPad with BRAT

1. Save any open Arbor edits. Disable Arbor in **Settings → Community plugins**, but **do not uninstall it**.
2. Install and enable **BRAT** from Community plugins if you do not have it yet.
3. Open **BRAT settings → Add beta plugin** and enter `Kpyruy/Arbor-beta` (or this repository's URL).
4. If BRAT shows a version selector, choose **0.3.1-beta.3**. Add/install the plugin.
5. Re-enable Arbor in Community plugins. If Obsidian still shows the old build, fully close and reopen the app. Check that Arbor's version is **0.3.1-beta.3**.

This build keeps the plugin ID `arbor`. BRAT replaces only the plugin's program files; it does not require access to the hidden `.obsidian` folder and does not replace `data.json` or your notes. Keep your normal vault backup. Do not uninstall the existing plugin just to try this build.

While testing, do not update Arbor from Community plugins: that may restore the stable build. You do not need a GitHub token for this public repository.

## Quick test

- **Branch scrolling:** read a long focused card to its end, then scroll up/down to earlier and later neighboring cards without zooming out. Each column should scroll independently, without moving the parent column or snapping back after a normal redraw.
- **Keyboard:** in both Branch Editor and Tree Overview, switch between the full keyboard, floating keyboard and hidden keyboard. The bottom buttons should return to their normal position without reloading.
- **Pinch:** in Branch Editor, slowly zoom in and out on a short and a long card, then reverse direction and release. Try scrolling with one finger before adding the second finger. Watch for jumps or a sudden recenter when releasing.
- **Drag targets:** with the keyboard visible in split view, drag an excerpt onto a card, then across the gap to **New block beside** or **New child block**. The independent targets should remain reachable without covering the bottom buttons; in tight spaces they can sit side by side.
- **Result and regression:** each drop should create one block, preserve the source reference and leave the original unchanged. Check that Tree Overview navigation still feels good and switching views keeps the zoom.

Moving completely outside the Arbor pane should clear the targets. Report feedback in [Arbor issue #7](https://github.com/Kpyruy/Arbor/issues/7).

## Returning to stable

Remove this repository from BRAT's beta-update list **without uninstalling Arbor**. Once the stable fix is released in the main repository, update Arbor normally through Community plugins. Until then, you can keep this beta or reinstall the stable program files while preserving `data.json`.

## Build identity

Source baseline: [38dcf4e](https://github.com/Kpyruy/Arbor/commit/38dcf4e32e49a66a14501a609deb1a1e883d2ea7), plus the unreleased keyboard/pinch/drop-layout and touch-column scrolling fixes in this candidate. Those follow-up source changes are not yet committed upstream; the baseline link alone does not contain them. This repository's tagged distribution records the exact tested program files; the distribution manifest changes the version only.

The candidate passed **1177 automated tests**, scoped and clean-source lint/build checks, and **seven full-production-view native Chromium configurations** covering zoom, RTL and compact layouts. A 50-paragraph card was read to its end with native swipes; a 30-second selection/scroll stress check also passed. The clean-source checks reused installed dependencies, not a fresh CI install. Browser checks do not replace a real iPad test. The tester reported improved pinch and keyboard behavior with the previous candidate; physical iPad confirmation of the new column scrolling is still needed.

SHA-256 of the tested program files:

```text
main.js     d4c4ba3a2b8b369f92284ae61c14b05cc39a33ada25c800906c42ecc8eeb9180
styles.css  c4f269dd96de12f7126bb99c8f8bd64d16d78f8fac323c8230edc2ab351e661b
```

Release assets are `main.js`, `styles.css`, and `manifest.json`. Root copies are provided for compatibility; `manifest-beta.json` points to the same beta version for older BRAT clients. Source development and stable releases remain in the main repository. License: MIT.
