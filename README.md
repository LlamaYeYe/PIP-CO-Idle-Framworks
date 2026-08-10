# PIP-CO Idle Frameworks

PIP-CO Idle Frameworks for The Wand Company Pip-Boy 3000.

## V23.54

This package preserves the compact V23.49 lazy-loaded Mesmetron architecture and the V23.54 native-page wake fix.

### Current behavior

- Built-in PIP-BOY 3000 idle screensaver support.
- Optional Mesmetron screensavers are discovered from Mesmetron when installed.
- Mesmetron previews are intentionally disabled.
- Mesmetron screensavers run through the real 2-minute idle trigger.
- The underlying Pip-Boy page is suspended before a Mesmetron idle starts so native UI does not show through.
- On wake, the native page is freshly reloaded instead of restoring an already-removed page object.
- Mesmetron itself is not modified.

## Installation

The website/installer should install the files in `assets/` to:

`HOLO/FALLOUT_SCREENSAVER/`

Mesmetron remains a separate optional installation under:

`HOLO/MESMETRON/`
