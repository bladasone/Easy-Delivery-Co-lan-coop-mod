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
