# Arbor beta builds

Testing-only distribution of [Arbor](https://github.com/Kpyruy/Arbor). This repository is **not** a second plugin or a Community Plugins release.

Current test build: **[0.3.1-beta.4](https://github.com/Kpyruy/Arbor-beta/releases/tag/0.3.1-beta.4)** — restores invisible descendant cards in Branch Editor and removes the detached tablet column scrollbar, while retaining independent scrolling, keyboard, pinch zoom and drop-target fixes.

Already using this repository in BRAT? Check for beta plugin updates. If your version is pinned to an older beta, change the selected version to **0.3.1-beta.4**. Restart Obsidian and check the installed Arbor version; no uninstall or manual file replacement is needed.

## Install on iPad with BRAT

1. Save any open Arbor edits. Disable Arbor in **Settings → Community plugins**, but **do not uninstall it**.
2. Install and enable **BRAT** from Community plugins if you do not have it yet.
3. Open **BRAT settings → Add beta plugin** and enter `Kpyruy/Arbor-beta` (or this repository's URL).
4. If BRAT shows a version selector, choose **0.3.1-beta.4**. Add/install the plugin.
5. Re-enable Arbor in Community plugins. If Obsidian still shows the old build, fully close and reopen the app. Check that Arbor's version is **0.3.1-beta.4**.

This build keeps the plugin ID `arbor`. BRAT replaces only the plugin's program files; it does not require access to the hidden `.obsidian` folder and does not replace `data.json` or your notes. Keep your normal vault backup. Do not uninstall the existing plugin just to try this build.

While testing, do not update Arbor from Community plugins: that may restore the stable build. You do not need a GitHub token for this public repository.

## Quick test

- **Card visibility:** navigate from root to child and grandchild, then switch to a different branch and back. Descendant cards must remain visible; the breadcrumb alone is not sufficient. The beta.3 regression left columns transparent, rather than deleting their cards.
- **Branch scrolling:** read a long focused card to its end, then scroll up/down to earlier and later neighboring cards without zooming out. Each column should scroll independently, without moving the parent column or snapping back after a normal redraw.
- **Keyboard:** in both Branch Editor and Tree Overview, switch between the full keyboard, floating keyboard and hidden keyboard. The bottom buttons should return to their normal position without reloading.
- **Pinch:** in Branch Editor, slowly zoom in and out on a short and a long card, then reverse direction and release. Try scrolling with one finger before adding the second finger. Watch for jumps or a sudden recenter when releasing.
- **Drag targets:** with the keyboard visible in split view, drag an excerpt onto a card, then across the gap to **New block beside** or **New child block**. The independent targets should remain reachable without covering the bottom buttons; in tight spaces they can sit side by side.
- **Result and regression:** each drop should create one block, preserve the source reference and leave the original unchanged. Check that Tree Overview navigation still feels good and switching views keeps the zoom.

Moving completely outside the Arbor pane should clear the targets. Report feedback in [Arbor issue #7](https://github.com/Kpyruy/Arbor/issues/7).

## Returning to stable

Remove this repository from BRAT's beta-update list **without uninstalling Arbor**. Once the stable fix is released in the main repository, update Arbor normally through Community plugins. Until then, you can keep this beta or reinstall the stable program files while preserving `data.json`.

## Build identity

Source: [1a594f3](https://github.com/Kpyruy/Arbor/commit/1a594f3cee4bfbd2874b1e8c6ffe28b61d2e90b9), containing the viewport, keyboard/pinch/drop-layout, independent touch-column scrolling and descendant-visibility fixes. This repository's tagged distribution records the exact tested program files; the distribution manifest changes the version only. Stable Arbor remains 0.3.1.

The candidate passed **1180 automated tests** and standard lint/build checks in a clean staged-source snapshot (using installed dependencies, not a fresh CI install). The installed plugin was also tested in actual Obsidian/Electron with tablet, portrait, split-pane and phone-sized touch emulation: descendant visibility, 11 native icon controls, navigation, zoom, scrolling, text/image drops, editing and reopen persistence. A 50-paragraph card was read to its end with 17 native swipes. The final scrollbar-only change was separately verified in that installed host without disabling scrolling. These checks do not certify physical iPadOS/WebKit, software-keyboard transitions or hardware smoothness; those still need the tester's confirmation.

SHA-256 of the tested program files:

```text
main.js     53ea758e79622291c83ab7750ee417558ef07bd8eb5c574823318ec1d06f9d49
styles.css  796938260e14413fa9af0e44e4d21a6acabc8a9744217e6704e730951a9f92d8
```

Release assets are `main.js`, `styles.css`, and `manifest.json`. Root copies are provided for compatibility; `manifest-beta.json` points to the same beta version for older BRAT clients. Source development and stable releases remain in the main repository. License: MIT.
