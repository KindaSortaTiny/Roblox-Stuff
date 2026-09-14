# Rodus

A personal rewrite of the original **Rodus** UI.
Made for Delta & Xeno; should work for ALL executors.

> ⚠️ Personal-use project. No support, issue handling, or guarantees are provided.

> Credit and apologies to the original developer of Rodus.

> My version is re-themed with new UI functions added such as dropdowns, multi-select, toggles, etc.

<details>
<summary>UI Preview</summary>
<br>

![Rodus UI Preview](https://i.imgur.com/RrFcby2.png)
</details>

<details>
<summary>Showcase Source</summary>

<br>

```lua
local Rodus = loadstring(game:HttpGet("https://raw.githubusercontent.com/KindaSortaTiny/Roblox-Stuff/refs/heads/main/UIs/Rodus/Rodus.lua"))()

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

    for target, enabled in pairs(selectedTargets) do
        print(target, enabled)
    end
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

</details>

## Controls
- `LeftControl` — Show/hide UI
