# EasyDeliveryCoLanCoop v0.3.0

LAN coop mod for Easy Delivery Co (BepInEx 5).

**Fork of [ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod](https://github.com/ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod)** — adapted for the latest game version.

## What is new

- **Full compatibility with the latest Easy Delivery Co update.**
- Updated reflection calls for new menu types: `ChooseExe`, `ScreenSystem`, `DesktopDotExe`, `ScreenProgram` (replaces old `sMainMenu`/`sMenuManager`/`sSaveMenu`).
- Fixed item carrying: now uses `sCharacterInteraction.payloadPivot` + `sItemManager.heldItem` (old `sCharacterController.pickupPoint` removed).
- Fixed `ScreenSystem.Resume(null)` to properly exit the main menu.
- Added missing Unity assembly references: InputModule, InputLegacyModule, UIElementsModule, UI, TextMeshPro, AnimationModule.
- Fixed all deprecated Unity API calls (CS0618 warnings: `FindObjectOfType` → `FindFirstObjectByType`/`FindAnyObjectByType`, `Rigidbody.drag` → `linearDamping`, `Rigidbody.velocity` → `linearVelocity`).
- Clean build: 0 errors, 0 warnings.

## Installation

1. Install BepInEx 5 (Mono) into the game folder.
2. Copy `EasyDeliveryCoLanCoop.dll` to:
   `BepInEx/plugins/EasyDeliveryCoLanCoop/`
3. Launch game normally or with `--lancoop-server` / `--lancoop-client`.

## Compatibility notes

- Host and client should use the same mod version.
- Project status: experimental.
- Requires the latest Easy Delivery Co version (with `ChooseExe`/`ScreenSystem` menu types).

## Recommended release asset

Attach this file to the GitHub Release:

- `EasyDeliveryCoLanCoop-v0.3.0.zip`

Local path in this repo:

- `releases/EasyDeliveryCoLanCoop-v0.3.0.zip`
