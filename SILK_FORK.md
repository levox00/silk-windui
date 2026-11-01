# Silk WindUI fork

A PS99-focused fork of [WindUI](https://github.com/Footagesus/WindUI), preserving its MIT license and original attribution.

`dist/SilkWindUI.luau` is the tested, self-contained runtime based on the WindUI snapshot bundled with the PS99 Hub. The upstream build header identifies the snapshot as v1.6.65; the original vendored filename recorded it as 1.6.66. It does not require this checkout at runtime. The matching focused changes are also represented in `src/`. The upstream `dist/main.lua` remains the upstream build.

The fork adds theme keys for active and inactive tab text/icons and 1% background-image transparency precision. The PS99 Hub supplies its own theme, artwork, and layout when consuming the library; those are not embedded in this library.

Roblox usage (replace the commit with the desired revision):

```lua
local url = "https://raw.githubusercontent.com/levox00/ps99-silk-windui/<commit>/dist/SilkWindUI.luau"
local chunk = game:HttpGet(url)
local factory, err = loadstring(chunk, "SilkWindUI")
assert(factory, err)
local WindUI = factory()
```

The runtime still contains WindUI's optional upstream icon and key-system integrations. Network and executor support depend on the environment. No gameplay, account data, or user settings are included here.
