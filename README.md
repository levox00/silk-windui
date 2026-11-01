> **Silk WindUI** is a customizable WindUI fork for Roblox interfaces across games. See [SILK_FORK.md](SILK_FORK.md) for the runtime, image layer API, attribution, and changes. The original upstream documentation follows.

<!--<h1 align="center">WindUI</h1> -->

<!--
<picture>
    <source srcset="docs/banner-dark.webp" media="(prefers-color-scheme: dark)">
    <source srcset="docs/banner-light.webp" media="(prefers-color-scheme: light)">
    <img src="docs/banner-light.webp" alt="WindUI Banner">
</picture>-->

<img src="docs/WindUI – Themes.png" alt="WindUI Banner">

I might rewrite this project from scratch later.

> [!WARNING]
> This WindUI was not inspired by, and the name has nothing to do with UI Frameworks

> [!WARNING]
> WindUI is currently in Beta.
> This project is still under active development. Bugs, issues, and unstable features may occur. We’re constantly working on improvements, so please be patient and report any problems you encounter.

## Credits

#### Icons (https://github.com/Footagesus/Icons)

- [Lucide-Icons](https://github.com/lucide-icons/lucide)
- [Craft Icons](https://www.figma.com/community/file/1415718327120418204)
- [Geist Icons](https://vercel.com/geist/icons)
- [Solar Icons](https://icones.js.org/collection/solar)
- [SF Symbols](https://sf-symbols-one.vercel.app/)

### Links

- [Discord Server](https://discord.gg/ftgs-development-hub-1300692552005189632)
- [Documentation](https://footagesus.github.io/treehub-web/docs/windui)
- [Installation](https://footagesus.github.io/WindUI-Docs/docs/installation)
- [Example](/main_example.lua) (wip)
    ```luau
    loadstring(game:HttpGet('https://raw.githubusercontent.com/Footagesus/WindUI/refs/heads/main/main_example.lua'))()
    ```

### Window handle positioning

Offsets are pixel `Vector2` values relative to the bottom edge. Positive Y moves down; positive X moves right. The resize handle is centered on the bottom-right corner, while the drag bar starts below the window.

```lua
local window = WindUI:CreateWindow({
    -- Other window options...
    DragHandleOffset = Vector2.new(0, 4),
    ResizeHandleOffset = Vector2.new(0, 0),
    DragFrameSize = 160,
})

-- Change either position at runtime; nil leaves that handle unchanged.
window:SetHandleOffsets(Vector2.new(0, 8), Vector2.new(4, 4))
```

The background and optional image layers are clipped to the window. Handle offsets do not enlarge the background.
