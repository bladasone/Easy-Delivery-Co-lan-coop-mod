# EasyDeliveryCoLanCoop

LAN-кооп мод для Easy Delivery Co на базе BepInEx 5.

Текущая версия: **0.3.0**

**Форк от [ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod](https://github.com/ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod).**
Адаптирован под новую версию игры (меню, взаимодействие, сохранения).

## Описание репозитория

EasyDeliveryCoLanCoop — это мод, который добавляет LAN-кооператив в Easy Delivery Co: подключение Host/Client, синхронизацию игроков и машин, базовую синхронизацию прогресса и расширенную синхронизацию автомобильных звуков.

Репозиторий предназначен для:

- использования готовой сборки мода;
- сборки из исходников;
- совместной доработки и отладки сетевой части.

Статус проекта: experimental (активная разработка).

## Что умеет мод

- LAN-сетевой слой Host/Client поверх UDP
- Автообнаружение хоста в локальной сети (broadcast)
- Синхронизация игроков, машин и груза в машине
- Синхронизация денег и части прогресса через ключи сохранений
- Синхронизация звуков машины:
  - клаксон
  - шины/скольжение
  - удары/столкновения
- Режим работы игры в фоне (не останавливается при потере фокуса)

## Изменения в v0.3.0 (форк)

- Адаптация под новую версию Easy Delivery Co (обновлённые типы меню, скрипты контроллера, система предметов)
- Обновлены рефлексивные вызовы: новые типы `ChooseExe`, `ScreenSystem`, `DesktopDotExe`, `ScreenProgram` вместо старых `sMainMenu`/`sMenuManager`/`sSaveMenu`
- Исправлен перенос предметов: `sCharacterController.pickupPoint` → `sCharacterInteraction.payloadPivot` + `sItemManager.heldItem`
- Исправлен вызов `ScreenSystem.Resume(null)` для корректного выхода из главного меню
- Обновлены HintPath в `.csproj` для новых путей сборок игры
- Добавлены недостающие Reference: `UnityEngine.InputModule`, `InputLegacyModule`, `UIElementsModule`, `UI`, `TextMeshPro`, `AnimationModule`
- Исправлены предупреждения об устаревших API Unity (CS0618)

## Ограничения

- Мод в статусе experimental, не все игровые системы реплицируются 1:1
- Авторитет у хоста: хост принимает/применяет ключевые изменения и рассылает снапшоты
- Возможны рассинхроны на сложной физике и нестандартных сценариях

## Требования

- Windows
- Easy Delivery Co
- BepInEx 5 (Mono)

## Установка

1. Установите BepInEx 5 в папку игры.
2. Скопируйте `EasyDeliveryCoLanCoop.dll` в:
   - `BepInEx/plugins/EasyDeliveryCoLanCoop/`
3. Если Harmony не подхватывается автоматически, убедитесь, что `0Harmony.dll` доступен (обычно через BepInEx, либо рядом с плагином).

## Быстрый старт

### Вариант 1: через конфиг

Файл конфига:
- `BepInEx/config/EasyDeliveryCoLanCoop.cfg`

Параметр `Mode`:
- `Off`
- `Host`
- `Client`

Для клиента также задайте `HostAddress` и `Port`.

### Вариант 2: через аргументы запуска (рекомендуется)

Поддерживаемые аргументы:
- `--lancoop-server` или `--lancoop-host`
- `--lancoop-client`
- `--lancoop-off`

Пример:
- `EasyDeliveryCo.exe --lancoop-server`

## Готовые bat-скрипты

В корне проекта есть:

- `run_lancoop_server.bat`
- `run_lancoop_client.bat`
- `run_lancoop_off.bat`

Примеры запуска из PowerShell:

- `.\run_lancoop_server.bat "D:\Easy Delivery Co\EasyDeliveryCo.exe"`
- `.\run_lancoop_client.bat "D:\Easy Delivery Co\EasyDeliveryCo.exe"`

## Важные настройки

### Сеть

- `Mode`
- `Port`
- `HostAddress`
- `TickRate`
- `ClientTimeoutSeconds`

### LAN discovery

- `AutoDiscovery`
- `DiscoveryPort`
- `DiscoveryIntervalMs`

### Звуки машин

- `CarSoundSyncEnabled`
- `CarSoundSyncMode`
  - `All`: клаксон + шины + удары
  - `HornOnly`: только клаксон
- `CarSoundSyncMinIntervalSeconds`

### Прогресс/сейв

- `SaveKeySyncEnabled`
- `SaveKeyDenySubstrings`
- `ClientReceivesHostSaveOnJoin`
- `ClientWipeLocalSaveOnJoin`

### Позиции игроков

- `Positions.Enabled`
- `Positions.SaveIdOverride`
- `Positions.ClientTeleportOnJoin`

### Отладка

- `Debug.DebugLogs`
- `Debug.DebugLogIntervalSeconds`

## Логи

Ищите логи BepInEx в стандартной папке игры.

Полезные маркеры в логах:

- `UDP host listening`
- `UDP client started`
- `Client registered`
- `Snapshot send / Snapshot recv`
- `CarSfx send / CarSfx recv / CarSfx relay`

## Сборка из исходников

1. Положите необходимые зависимости в папку `lib` (см. `lib/README.md`):
   - `BepInEx.dll`
   - `BepInEx.Harmony.dll`
   - `0Harmony.dll`
2. Выполните:

   ```
   dotnet build -c Release
   ```

3. Готовая сборка:

   ```
   bin/Release/netstandard2.1/EasyDeliveryCoLanCoop.dll
   ```

## Документы проекта

- Changelog: [CHANGELOG.md](CHANGELOG.md)
- Contributing guide: [CONTRIBUTING.md](CONTRIBUTING.md)

## Лицензия

Проект распространяется по лицензии MIT.
См. [LICENSE](LICENSE).

## Обратная связь

При баг-репорте прикладывайте:

- версию мода
- логи хоста и клиента
- шаги воспроизведения
- какие настройки в cfg использовались

---

# English

LAN co-op mod for Easy Delivery Co built with BepInEx 5.

Current version: **0.3.0**

**Fork of [ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod](https://github.com/ARMADA2025AA11/Easy-Delivery-Co-lan-coop-mod).**
Adapted for the latest game version (menu, interaction, save changes).

## Repository Description

EasyDeliveryCoLanCoop adds LAN multiplayer to Easy Delivery Co with Host/Client networking, player/car sync, partial progression sync, and extended vehicle SFX sync.

This repository is intended for:

- using the released DLL;
- building from source;
- collaborative networking/mod development.

Project status: experimental.

## Features

- UDP-based LAN Host/Client networking
- Automatic host discovery over LAN broadcast
- Player, car, and in-car cargo synchronization
- Money and partial save/progression synchronization
- Vehicle sound synchronization:
  - horn
  - tire/skid sounds
  - impact/crash sounds
- Runs in background (does not stop when window loses focus)

## v0.3.0 Changes (fork)

- Adapted for the latest Easy Delivery Co version (updated menu types, controller scripts, item system)
- Updated reflection calls: new types `ChooseExe`, `ScreenSystem`, `DesktopDotExe`, `ScreenProgram` replacing old `sMainMenu`/`sMenuManager`/`sSaveMenu`
- Fixed item carrying: `sCharacterController.pickupPoint` → `sCharacterInteraction.payloadPivot` + `sItemManager.heldItem`
- Fixed `ScreenSystem.Resume(null)` call for proper main menu exit
- Updated `.csproj` HintPath for new game assembly paths
- Added missing References: `UnityEngine.InputModule`, `InputLegacyModule`, `UIElementsModule`, `UI`, `TextMeshPro`, `AnimationModule`
- Fixed deprecated Unity API warnings (CS0618)

## Requirements

- Windows
- Easy Delivery Co
- BepInEx 5 (Mono)

## Installation

1. Install BepInEx 5 into the game folder.
2. Copy `EasyDeliveryCoLanCoop.dll` into:
   - `BepInEx/plugins/EasyDeliveryCoLanCoop/`
3. If Harmony is not auto-resolved, ensure `0Harmony.dll` is available (usually via BepInEx or next to the plugin).

## Quick Start

### Option 1: Config mode

Config file:
- `BepInEx/config/EasyDeliveryCoLanCoop.cfg`

Mode values:
- `Off`
- `Host`
- `Client`

For client mode also set `HostAddress` and `Port`.

### Option 2: Launch arguments (recommended)

Supported args:
- `--lancoop-server` or `--lancoop-host`
- `--lancoop-client`
- `--lancoop-off`

Example:
- `EasyDeliveryCo.exe --lancoop-server`

## Included Launcher Scripts

- `run_lancoop_server.bat`
- `run_lancoop_client.bat`
- `run_lancoop_off.bat`

PowerShell examples:

- `.\run_lancoop_server.bat "D:\Easy Delivery Co\EasyDeliveryCo.exe"`
- `.\run_lancoop_client.bat "D:\Easy Delivery Co\EasyDeliveryCo.exe"`

## Important Settings

### Network

- `Mode`
- `Port`
- `HostAddress`
- `TickRate`
- `ClientTimeoutSeconds`

### LAN Discovery

- `AutoDiscovery`
- `DiscoveryPort`
- `DiscoveryIntervalMs`

### Vehicle Sounds

- `CarSoundSyncEnabled`
- `CarSoundSyncMode`
  - `All`: horn + tires + impacts
  - `HornOnly`: horn only
- `CarSoundSyncMinIntervalSeconds`

### Save/Progress

- `SaveKeySyncEnabled`
- `SaveKeyDenySubstrings`
- `ClientReceivesHostSaveOnJoin`
- `ClientWipeLocalSaveOnJoin`

### Player Positions

- `Positions.Enabled`
- `Positions.SaveIdOverride`
- `Positions.ClientTeleportOnJoin`

### Debug

- `Debug.DebugLogs`
- `Debug.DebugLogIntervalSeconds`

## Logs

Use BepInEx logs from the game folder.

Useful log markers:

- `UDP host listening`
- `UDP client started`
- `Client registered`
- `Snapshot send / Snapshot recv`
- `CarSfx send / CarSfx recv / CarSfx relay`

## Build From Source

1. Put required dependencies into `lib` (see `lib/README.md`):
   - `BepInEx.dll`
   - `BepInEx.Harmony.dll`
   - `0Harmony.dll`
2. Run:

   ```
   dotnet build -c Release
   ```

3. Build output:

   ```
   bin/Release/netstandard2.1/EasyDeliveryCoLanCoop.dll
   ```

## Project Documents

- Changelog: [CHANGELOG.md](CHANGELOG.md)
- Contributing: [CONTRIBUTING.md](CONTRIBUTING.md)

## License

MIT License.
See [LICENSE](LICENSE).

## Feedback

When reporting bugs, include:

- mod version
- host/client logs
- reproduction steps
- relevant config values
