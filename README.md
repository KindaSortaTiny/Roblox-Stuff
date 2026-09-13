# Rodus

Personal rewrite of **Rodus**.

> ⚠️ Personal use only. No support, issues, or guarantees.
## Controls
- `LeftControl` — show/hide UI

## Showcase
```lua
local Rodus = loadstring(game:HttpGet("https://raw.githubusercontent.com/KindaSortaTiny/RodusUI/refs/heads/main/UILib.lua"))()
local Window = Rodus("Rodus")
local Main = Window.CreateTab("Main")
local Settings = Window.CreateTab("Settings")

local autoFarm = false
local selectedMode = "Legit"
local selectedTargets = {}

Main.CreateLabel(Main, "Automation")
Main.CreateButton(Main, "Print Status", function()
    print("Auto Farm:", autoFarm)
    print("Mode:", selectedMode)
end)

Main.CreateToggle(Main, "Auto Farm", function()
    autoFarm = not autoFarm
    print("Auto Farm:", autoFarm)
end)

Settings.CreateLabel(Settings, "Settings")
Settings.CreateSideDropButton(Settings, "Mode", {
    "Legit",
    "Hybrid",
    "Aggressive"
}, function(option)
    selectedMode = option
    print("Selected mode:", option)
end)

Settings.CreateSideDropToggle(Settings, "Targets", {
    "Players",
    "NPCs",
    "Bosses"
}, function(option)
    selectedTargets[option] = not selectedTargets[option]
    print(option, selectedTargets[option])
end)
```
