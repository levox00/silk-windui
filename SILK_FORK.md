# Silk WindUI fork

A general-purpose fork of [WindUI](https://github.com/Footagesus/WindUI), preserving its MIT license and original attribution.

`dist/SilkWindUI.luau` is the tested, self-contained runtime based on the WindUI snapshot bundled with the PS99 Hub. The upstream build header identifies the snapshot as v1.6.65; the original vendored filename recorded it as 1.6.66. It does not require this checkout at runtime. The matching focused changes are also represented in `src/`. The upstream `dist/main.lua` remains the upstream build.

The fork adds theme keys for active and inactive tab text/icons 1% background-image transparency precision, and keeps the reported theme synchronized with the window theme. Consumers supply their own theme and artwork; they are not embedded in this library.

Roblox usage (replace the commit with the desired revision):

```lua
local url = "https://raw.githubusercontent.com/levox00/silk-windui/<commit>/dist/SilkWindUI.luau"
local chunk = game:HttpGet(url)
local factory, err = loadstring(chunk, "SilkWindUI")
assert(factory, err)
local WindUI = factory()
```

The runtime still contains WindUI's optional upstream icon and key-system integrations. Network and executor support depend on the environment. No gameplay, account data, or user settings are included here.

## Image layers

`window:SetBackgroundImage(assetId)` sets the window background. `window:SetBackgroundImageTransparency(0.25)` changes its transparency. For additional named, clipped, non-interactive layers:

```lua
window:SetImageLayer("petals", { Image = assetId, Layer = "Above", Transparency = 0.12 })
window:SetImageLayer("texture", { Image = textureId, Layer = "Below", Transparency = 0.5, ZIndex = 2 })
window:RemoveImageLayer("petals")
```

`Layer` is `Above` (default) or `Below`. Optional `ZIndex`, `Position`, `Size`, and `ScaleType` control placement. Assets must already be valid Roblox/executor asset IDs; external image URLs need downloading and registration by the consuming script. Reusing a name replaces the old layer. Rendering and input behavior need testing in the target executor and device.
