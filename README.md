# PIP-CO Idle Frameworks

A configurable idle/screensaver framework for The Wand Company Pip-Boy 3000.

PIP-CO Idle Frameworks includes its built-in PIP-BOY 3000 falling-bomb
screensaver and can dynamically use compatible screensavers from separately
installed provider holotapes.

## Features

- 2-minute automatic idle activation
- Built-in PIP-BOY 3000 falling-bomb screensaver
- Optional Mesmetron integration
- Optional Pipquarium integration
- Live preview from the PIP-CO menu
- Fullscreen automatic-idle runner
- Provider entries only appear when the matching provider holotape is installed
- PIP-CO owns wake/exit controls while a provider is running as an idle
- Provider holotapes retain their own native behavior when opened normally
- Radio/audio detection remains read-only

## Optional providers

### Mesmetron

Mesmetron is not bundled with PIP-CO Idle Frameworks.

If `HOLO/MESMETRON/TITLE.JS` is installed, PIP-CO reads Mesmetron's current
screensaver list dynamically. Removing Mesmetron removes those entries from
PIP-CO automatically.

### Pipquarium

Pipquarium is not bundled with PIP-CO Idle Frameworks.

If a compatible PIP-CO-safe Pipquarium installation is present at
`HOLO/PIPQUARIUM/APP.JS`, PIP-CO adds `Pipquarium` to the idle-provider list.
Removing Pipquarium removes that entry automatically.

Pipquarium is loaded only when its preview or automatic idle actually starts;
its renderer is not embedded in the PIP-CO menu/service.

## Installation

Install through pip-boy.com / the holotape registry.

The installer creates the device-side `.info` registration from `metadata.json`.
The public runtime does not create or overwrite `APPINFO/*.info`.

Installed PIP-CO files live under:

`HOLO/FALLOUT_SCREENSAVER/`

Mesmetron and Pipquarium are optional independent holotapes and are not included
inside this package.

## Controls

Inside PIP-CO Idle Frameworks:

- Left wheel: navigate
- Left wheel press: select
- `Preview Screensaver`: preview the selected idle
- `< Back`: return

While an idle is active, PIP-CO owns the wake/exit controls rather than allowing
provider-specific wheel modifiers to change the provider state.

## Idle choices

With no optional providers installed, only the built-in `PIP-BOY 3000`
screensaver is shown.

When Mesmetron and/or Pipquarium are installed, their compatible entries are
added automatically.

Only one idle provider is active at a time.

## Low-memory architecture

The runtime is split so the main menu, persistent idle service, built-in bomb
renderer, Mesmetron adapter, Pipquarium adapter, and fullscreen runner are
separate files.

Heavy renderer code is loaded only when needed. This avoids keeping provider
renderers in the main menu's memory scope and improves repeated
preview/idle/wake/reopen stability on the memory-constrained Pip-Boy.

## Compatibility

The integration does not bundle or rewrite Mesmetron or Pipquarium renderer
assets. Each provider remains independently installable.

PIP-CO does not replace `Pip.audioStart`, `Pip.bootAnimation`, `Pip.CURRENT`,
or `Pip.blitOptions`.

## Hardware validation

The REWRITE2I architecture was hardware-tested with:

- the built-in PIP-BOY 3000 idle
- Mesmetron detection, previews, automatic idle, and wake/exit
- Pipquarium detection, preview, automatic idle, and wake/exit
- provider uninstall detection
- repeated navigation and reopening without the earlier LOW MEMORY crash

The known Mesmetron Spiral JIT warning originates in the Spiral renderer and is
not a PIP-CO LOW_MEMORY failure.
