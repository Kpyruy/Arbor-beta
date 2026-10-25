# Arbor beta builds

Testing-only distribution of [Arbor](https://github.com/Kpyruy/Arbor). This repository is **not** a second plugin or a Community Plugins release.

Current test build: **[0.3.1-beta.5](https://github.com/Kpyruy/Arbor-beta/releases/tag/0.3.1-beta.5)** — choose between limited-height cards and full-content cards, with readable width-only Active zoom. Includes the earlier card-visibility, independent scrolling, keyboard, pinch and drop-target fixes.

Already using this repository in BRAT? Check for beta plugin updates. If your version is pinned to an older beta, change the selected version to **0.3.1-beta.5**. Restart Obsidian and check the installed Arbor version; no uninstall or manual file replacement is needed.

## Install on iPad with BRAT

1. Save any open Arbor edits. Disable Arbor in **Settings → Community plugins**, but **do not uninstall it**.
2. Install and enable **BRAT** from Community plugins if you do not have it yet.
3. Open **BRAT settings → Add beta plugin** and enter `Kpyruy/Arbor-beta` (or this repository's URL).
4. If BRAT shows a version selector, choose **0.3.1-beta.5**. Add/install the plugin.
5. Re-enable Arbor in Community plugins. If Obsidian still shows the old build, fully close and reopen the app. Check that Arbor's version is **0.3.1-beta.5**.

This build keeps the plugin ID `arbor`. BRAT replaces only the plugin's program files; it does not require access to the hidden `.obsidian` folder and does not replace `data.json` or your notes. Keep your normal vault backup. Do not uninstall the existing plugin just to try this build.

While testing, do not update Arbor from Community plugins: that may restore the stable build. You do not need a GitHub token for this public repository.

## Quick test

- **New reading mode:** choose **Settings → Arbor → Active card height → Fit content**. Read a very long active Branch Editor card to its end: the whole card should scroll naturally, without an internal text scrollbar. Inactive previews stay compact.
- **Active zoom:** enable it on the long card and scroll again. Text should remain readable, without fitting the entire height into the screen or repeatedly snapping back to the top.
- **Selection and preference:** switch between short/long neighboring cards, then reopen Obsidian. The selected height preference should persist. **Limited height** restores bounded cards with internal text scrolling and remains the default.
- **Regression:** check root → child → grandchild, pinch and Tree Overview. Editing still uses its separate textarea scrolling; the reading-card preference does not remove editor scrollbars.

Moving completely outside the Arbor pane should clear the targets. Report feedback in [Arbor issue #7](https://github.com/Kpyruy/Arbor/issues/7).

## Returning to stable

Remove this repository from BRAT's beta-update list **without uninstalling Arbor**. Once the stable fix is released in the main repository, update Arbor normally through Community plugins. Until then, you can keep this beta or reinstall the stable program files while preserving `data.json`.

## Build identity

Source: [37204b0](https://github.com/Kpyruy/Arbor/commit/37204b0846356f241505c2d58593745322e6ed77), adding the height preference, width-fit zoom and compact-layout stability fixes on top of beta.4. This repository's tagged distribution records the exact tested program files; the distribution manifest changes the version only. Stable Arbor remains 0.3.1.

The candidate passed **1199 automated tests** and standard lint/build checks in a clean staged-source snapshot (using installed dependencies, not a fresh CI install). The installed plugin was also checked in actual Obsidian/Electron: both native settings choices, desktop wheel scrolling, tablet/phone native touch scrolling, reaching paragraph 50, readable width-fit Active zoom, compact inactive previews and Tree roundtrip. The compact-phone zoom remained stable over 20 samples without resetting reading scroll. Existing Markdown notes and previous preferences were unchanged by QA. These checks do not certify physical iPadOS/WebKit, software-keyboard transitions or hardware smoothness; those still need the tester's confirmation.

SHA-256 of the tested program files:

```text
main.js     7f6a5a9383bced517488d733365b93c026e229cb39bd98a7ea2d69c0bec86453
styles.css  fd59a72f355264f828098adb9ea0f7932e13f87865ca3e05c91bfdd3eb60008f
```

Release assets are `main.js`, `styles.css`, and `manifest.json`. Root copies are provided for compatibility; `manifest-beta.json` points to the same beta version for older BRAT clients. Source development and stable releases remain in the main repository. License: MIT.
