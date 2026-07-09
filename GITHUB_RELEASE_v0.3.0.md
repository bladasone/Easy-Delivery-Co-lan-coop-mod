# EasyDeliveryCoLanCoop v0.3.0

LAN coop mod for Easy Delivery Co (BepInEx 5).

**Форк [ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod](https://github.com/ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod)** — адаптирован под новую версию игры.

---

## Что нового / What's new

- **Полная совместимость с последним обновлением Easy Delivery Co.**
- Обновлены рефлексивные вызовы для новых типов меню: `ChooseExe`, `ScreenSystem`, `DesktopDotExe`, `ScreenProgram` (вместо старых `sMainMenu`/`sMenuManager`/`sSaveMenu`).
- Исправлен перенос предметов: теперь используется `sCharacterInteraction.payloadPivot` + `sItemManager.heldItem` (старого `sCharacterController.pickupPoint` больше нет).
- Исправлен `ScreenSystem.Resume(null)` для корректного выхода из главного меню.
- Добавлены недостающие ссылки на сборки Unity: InputModule, InputLegacyModule, UIElementsModule, UI, TextMeshPro, AnimationModule.
- Исправлены все предупреждения об устаревших API Unity (CS0618).
- Чистая сборка: 0 ошибок, 0 предупреждений.

## Установка / Installation

1. Установите BepInEx 5 (Mono) в папку игры.
2. Скопируйте `EasyDeliveryCoLanCoop.dll` в:
   `BepInEx/plugins/EasyDeliveryCoLanCoop/`
3. Запустите игру с аргументом `--lancoop-server` (хост) или `--lancoop-client` (клиент).

## Запуск / Launch options

- `--lancoop-server` или `--lancoop-host` — запуск как сервер
- `--lancoop-client` — запуск как клиент
- `--lancoop-off` — отключить мод

## Совместимость / Compatibility

- Хост и клиент должны использовать одну версию мода.
- Статус проекта: experimental.
- Требуется последняя версия Easy Delivery Co (с новыми типами меню).

## Релизный архив / Release asset

Прикрепите к релизу:

- `EasyDeliveryCoLanCoop-v0.3.0.zip`

Файл в репозитории:

- `releases/EasyDeliveryCoLanCoop-v0.3.0.zip`
