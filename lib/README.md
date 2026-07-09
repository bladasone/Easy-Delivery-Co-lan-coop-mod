# Dependencies

Перед сборкой положите сюда DLL из дистрибутива BepInEx 5 для Unity Mono:

- `BepInEx.dll`
- `BepInEx.Harmony.dll`
- `0Harmony.dll`

**Где взять:** установите BepInEx 5 в папку игры, затем скопируйте из `BepInEx/core/`.

Unity-сборки берутся напрямую из папки Managed игры (прописаны в `.csproj` через HintPath).

## HintPath в .csproj

Unity-сборки в `.csproj` ссылаются на папку `..\Easy Delivery Co\`.  
Если у вас игра в другой папке — измените пути в Reference-блоках `.csproj`.

> ⚠️ **Внимание (RU):** В `.csproj` и других примерах используются относительные пути `..\Easy Delivery Co\...`. Для Steam-версии они могут не совпадать! Если название папки игры отличается (например, `EasyDeliveryCo steam version`), перед сборкой вам нужно:
> - Найти в `.csproj` все блоки `<Reference>` с `HintPath="..\Easy Delivery Co\..."` и изменить путь на правильный, **либо**
> - Переривязать DLL-ссылки напрямую в IDE (Visual Studio / Rider).

> ⚠️ **Warning (EN):** The `.csproj` and example files reference `..\Easy Delivery Co\...`. These paths may not match your Steam version! If your game folder has a different name (e.g., `EasyDeliveryCo steam version`), before building you need to:
> - Find all `<Reference>` blocks with `HintPath="..\Easy Delivery Co\..."` in `.csproj` and update the path, **or**
> - Re-bind the DLL references in your IDE (Visual Studio / Rider).

---

# Dependencies (English)

Before building, place the DLLs from BepInEx 5 distribution for Unity Mono here:

- `BepInEx.dll`
- `BepInEx.Harmony.dll`
- `0Harmony.dll`

**How to get them:** Install BepInEx 5 into the game folder, then copy from `BepInEx/core/`.

Unity assemblies are referenced directly from the game's Managed folder (specified in `.csproj` via HintPath).

## HintPath in .csproj

Unity assemblies in `.csproj` reference the `..\Easy Delivery Co\` folder.  
If your game is in a different folder — change the paths in the Reference blocks of `.csproj`.
