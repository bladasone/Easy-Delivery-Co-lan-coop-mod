# Contributing

Thanks for contributing to EasyDeliveryCoLanCoop.

## Development Setup

1. Install .NET SDK (compatible with `netstandard2.1` build workflow).
2. Put required game/BepInEx references into `lib/` (see `lib/README.md`).
3. Build:

   `dotnet build -c Release`

4. Copy resulting DLL to game plugin folder:

   `BepInEx/plugins/EasyDeliveryCoLanCoop/`

> ⚠️ **Warning:** The project's `.csproj` file has library dependency paths (`HintPath`) configured for the **non-Steam version** of Easy Delivery Co (folder: `..\Easy Delivery Co\`). If you have the **Steam version** installed, its folder may have a different name (e.g., `EasyDeliveryCo steam version`). If the build fails due to missing DLL references, you will need to:
> - Manually update the paths in `EasyDeliveryCoLanCoop.csproj` to match your game installation folder, **or**
> - Re-bind the game DLL references in your IDE (Visual Studio / Rider) to point to your Steam installation directory.

## Branching and Commits

- Use short, focused branches per feature/fix.
- Keep commits small and atomic.
- Commit message style:
  - `feat: ...`
  - `fix: ...`
  - `docs: ...`
  - `refactor: ...`

## Pull Request Checklist

- [ ] Code builds in `Release`.
- [ ] No unrelated file changes.
- [ ] README/CHANGELOG updated when behavior changes.
- [ ] Host/client compatibility impact described.
- [ ] Logs/examples added for network/audio related fixes.

## Reporting Bugs

When opening an issue, include:

- Mod version
- Game version
- Host and client logs
- Reproduction steps
- Config diff (network + sound settings)
- Expected vs actual behavior

## Coding Notes

- Prefer root-cause fixes over quick patches.
- Keep protocol changes backward-aware where practical.
- Avoid hardcoding machine-specific paths.
- Preserve existing style and naming in touched files.

## Testing Tips

- Validate both Host and Client paths.
- Test reconnect behavior.
- Test focus loss / background run behavior.
- For sound sync, test:
  - horn
  - skid/tire sounds
  - impact sounds
  - short/rapid repeated triggers

## Security and Safety

- Do not commit private credentials or local machine data.
- Keep binary blobs out of git unless required.

---

# На русском

## Сборка и разработка

1. Установите .NET SDK (совместимый с `netstandard2.1`).
2. Положите необходимые ссылки игры/BepInEx в папку `lib/` (см. `lib/README.md`).
3. Выполните сборку:

   `dotnet build -c Release`

4. Скопируйте полученную DLL в папку плагинов игры:

   `BepInEx/plugins/EasyDeliveryCoLanCoop/`

> ⚠️ **Внимание:** В файле `.csproj` пути к зависимостям игры (`HintPath`) настроены для **non-Steam версии** Easy Delivery Co (папка `..\Easy Delivery Co\`). Если у вас установлена **Steam-версия**, название папки игры может отличаться (например, `EasyDeliveryCo steam version`). Если при сборке возникают ошибки о недостающих DLL-ссылках, вам необходимо:
> - Вручную обновить пути в файле `EasyDeliveryCoLanCoop.csproj` в соответствии с расположением папки вашей игры, **либо**
> - Переривязать ссылки на DLL-библиотеки игры в вашей IDE (Visual Studio / Rider), указав на директорию Steam-версии.

## Ветвление и коммиты

- Используйте короткие, сфокусированные ветки для каждой фичи/исправления.
- Делайте маленькие и атомарные коммиты.
- Стиль сообщений коммитов:
  - `feat: ...`
  - `fix: ...`
  - `docs: ...`
  - `refactor: ...`

## Чек-лист для Pull Request

- [ ] Код собирается в режиме `Release`.
- [ ] Нет посторонних изменений файлов.
- [ ] README/CHANGELOG обновлены, если изменилось поведение.
- [ ] Описано влияние на совместимость Host/Client.
- [ ] Добавлены логи/примеры для исправлений сети и звуков.

## Баг-репорты

При открытии issue включите:

- версию мода
- версию игры
- логи хоста и клиента
- шаги для воспроизведения
- diff конфигурации (сетевые и звуковые параметры)
- ожидаемое и фактическое поведение

## Заметки о коде

- Предпочитайте исправления глубинных причин поверхностным патчам.
- Сохраняйте обратную совместимость при изменении протокола, где практично.
- Избегайте хардкода путей, специфичных для конкретной машины.
- Сохраняйте существующий стиль и именование в изменяемых файлах.

## Советы по тестированию

- Проверяйте обе ветки: Host и Client.
- Тестируйте поведение переподключения.
- Тестируйте потерю фокуса и фоновый режим.
- Для синхронизации звуков проверьте:
  - клаксон
  - звуки шин/скольжения
  - звуки ударов/столкновений
  - быстрые повторяющиеся срабатывания

## Безопасность и конфиденциальность

- Не коммитьте приватные учётные данные и данные, специфичные для вашей машины.
- Избегайте версионирования бинарных файлов, если это не необходимо.
