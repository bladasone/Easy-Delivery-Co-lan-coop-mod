# EasyDeliveryCoLanCoop v0.3.0

LAN-кооп мод для Easy Delivery Co на базе BepInEx 5.

**Форк [ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod](https://github.com/ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod)** — адаптирован под новую версию игры.

---

## Что нового

- **Полная совместимость с последним обновлением Easy Delivery Co.**
- Обновлены рефлексивные вызовы для новых типов меню: `ChooseExe`, `ScreenSystem`, `DesktopDotExe`, `ScreenProgram` (вместо старых `sMainMenu`/`sMenuManager`/`sSaveMenu`).
- Исправлен перенос предметов: теперь используется `sCharacterInteraction.payloadPivot` + `sItemManager.heldItem` (старого `sCharacterController.pickupPoint` больше нет).
- Исправлен `ScreenSystem.Resume(null)` для корректного выхода из главного меню.
- Добавлены недостающие ссылки на сборки Unity: InputModule, InputLegacyModule, UIElementsModule, UI, TextMeshPro, AnimationModule.
- Исправлены все предупреждения об устаревших API Unity (CS0618).
- Чистая сборка: 0 ошибок, 0 предупреждений.

## Установка

1. Установите BepInEx 5 (Mono) в папку игры.
2. Скопируйте `EasyDeliveryCoLanCoop.dll` в:
   `BepInEx/plugins/EasyDeliveryCoLanCoop/`
3. Запустите игру с аргументом `--lancoop-server` (хост) или `--lancoop-client` (клиент).

## Запуск

- `--lancoop-server` или `--lancoop-host` — запуск как сервер
- `--lancoop-client` — запуск как клиент
- `--lancoop-off` — отключить мод

## Совместимость

- Хост и клиент должны использовать одну версию мода.
- Статус проекта: experimental.
- Требуется последняя версия Easy Delivery Co (с новыми типами меню).

## Релизный архив

Прикрепите к релизу файл `EasyDeliveryCoLanCoop-v0.3.0.zip` из папки `releases/` репозитория.

---

# English

## What's new

- **Full compatibility with the latest Easy Delivery Co update.**
- Updated reflection calls for new menu types: `ChooseExe`, `ScreenSystem`, `DesktopDotExe`, `ScreenProgram` (replaces old `sMainMenu`/`sMenuManager`/`sSaveMenu`).
- Fixed item carrying: now uses `sCharacterInteraction.payloadPivot` + `sItemManager.heldItem` (old `sCharacterController.pickupPoint` removed).
- Fixed `ScreenSystem.Resume(null)` to properly exit the main menu.
- Added missing Unity assembly references: InputModule, InputLegacyModule, UIElementsModule, UI, TextMeshPro, AnimationModule.
- Fixed all deprecated Unity API calls (CS0618).
- Clean build: 0 errors, 0 warnings.

## Installation

1. Install BepInEx 5 (Mono) into the game folder.
2. Copy `EasyDeliveryCoLanCoop.dll` to: `BepInEx/plugins/EasyDeliveryCoLanCoop/`
3. Launch with `--lancoop-server` (host) or `--lancoop-client` (client).

## Launch options

- `--lancoop-server` / `--lancoop-host` — run as server
- `--lancoop-client` — run as client
- `--lancoop-off` — disable mod

## Compatibility

- Host and client must use the same mod version.
- Project status: experimental.
- Requires the latest Easy Delivery Co version.

## Release asset

Attach `EasyDeliveryCoLanCoop-v0.3.0.zip` from the `releases/` folder.
