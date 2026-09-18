# PIP-CO Idle Frameworks v1.2.0

Adds an automatic idle screensaver framework for **The Wand Company Pip-Boy 3000**, designed for **Fallout 3 / Fallout: New Vegas firmware 1.1.6**.

After **2 minutes of inactivity**, PIP-CO Idle Frameworks automatically launches the selected idle animation while keeping the normal Pip-Boy interface as lightweight as possible when the screensaver is not active.

## Features

* **2-minute automatic idle timer**
* **PIP-BOY 3000** built-in screensaver
* **Mesmetron** idle-animation support
* **Pipquarium** integration when the separate Pipquarium holotape is installed
* Only **one idle provider** is active at a time
* Live **Preview** option for supported idle animations
* Persistent idle-animation selection
* Custom PIP-CO Idle Frameworks artwork in the MISC menu
* Automatically exits the idle animation when either Pip-Boy wheel is used
* Detects existing radio/audio playback so the built-in screensaver does not interrupt audio it does not own

## Idle Animations

### Mesmetron

Adds the **Mesmetron** as an available PIP-CO idle animation, bringing a Fallout-style animated screensaver to the Pip-Boy when the device has been inactive.

Mesmetron **not bundled with PIP-CO Idle Frameworks**. When `HOLO/MESMETRON/APP.JS` is detected, it automatically becomes available as an idle-animation option.

### Pipquarium

Turns the Pip-Boy display into a small Fallout-style **aquarium screensaver** using the separately installed Pipquarium holotape.

Pipquarium is **not bundled with PIP-CO Idle Frameworks**. When `HOLO/PIPQUARIUM/APP.JS` is detected, it automatically becomes available as an idle-animation option.

A lightweight handoff is used so the Idle Framework can release unnecessary JavaScript state before Pipquarium starts.

## Memory & Stability

PIP-CO Idle Frameworks is designed around the limited Espruino memory available on the Pip-Boy 3000.

The framework uses deferred/lazy loading so the full screensaver system does not remain resident while using normal Pip-Boy menus.

## Controls

* **Left wheel — Rotate:** Move selection
* **Left wheel — Press:** Select, toggle, Preview, or Back
* **Either wheel during an active preview/screensaver:** Exit the idle animation

