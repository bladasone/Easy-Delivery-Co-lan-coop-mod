# EasyDeliveryCoLanCoop v0.3.0

## Highlights

- **Full compatibility with the latest Easy Delivery Co update.**
- Updated for new menu/UI types (`ChooseExe`, `ScreenSystem`, `DesktopDotExe`, `ScreenProgram`).
- Fixed item carrying via new `sCharacterInteraction.payloadPivot` + `sItemManager.heldItem` API.
- Fixed `ScreenSystem.Resume(null)` for proper main menu exit.
- Added missing Unity assembly references.
- Fixed all deprecated Unity API warnings (CS0618).

## Installation

1. Install BepInEx 5 (Mono) into the game folder.
2. Copy `EasyDeliveryCoLanCoop.dll` into:
   `BepInEx/plugins/EasyDeliveryCoLanCoop/`
3. Launch game normally or with one of the launch args.

## Notes

- This is an experimental LAN coop mod.
- Host/client should run the same mod version.
- Requires the latest Easy Delivery Co version.
