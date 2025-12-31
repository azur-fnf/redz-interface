
# ✨ Redz Interface V5

### UI Library Documentation

## 📖 Overview

**Redz Interface V5** is a lightweight and customizable UI library designed for Roblox scripts.
It follows the visual and structural standards of **Redz Library V5**, offering a modern interface system with built-in themes, tabs, notifications, dialogs, and persistent flags.

* Clean and modern UI
* Built-in theme system
* Modular tab & option system
* Optimized and lightweight
* Suitable for hubs and large scripts

**Source:**
`V5/Source.lua`

---

## 📦 Installation

Load the library using `loadstring`:

```lua
local Library = loadstring(game:HttpGet(
    "https://raw.githubusercontent.com/azur-fnf/redz-interface/refs/heads/main/V5/Source.lua"
))()
```

---

## 🪟 Creating a Window

```lua
local Window = Library:MakeWindow({
    Title = "My Hub",
    SubTitle = "by Developer",
    SaveFolder = "MyHub/V5"
})
```

### Window Configuration

| Property     | Type   | Description                        |
| ------------ | ------ | ---------------------------------- |
| `Title`      | string | Main window title                  |
| `SubTitle`   | string | Subtitle below the title           |
| `SaveFolder` | string | Folder used to save configurations |

---

## 🎨 Theme System

### Available Themes

* `Dark`
* `Darker`
* `Purple`

### Change Theme

```lua
Library:SetTheme("Dark")
```

### Validate Theme

```lua
Library:IsValidTheme("Dark")
```

---

## 📑 Tabs

### Create a Tab (Normal)

```lua
local MainTab = Window:MakeTab({
    Title = "Main",
    Icon = "Home"
})
```

### Create a Tab (Compact)

```lua
local MainTab = Window:MakeTab({ "Main", "Home" })
```

---

## 🔔 Notifications

```lua
Window:Notify({
    Title = "Notification",
    Content = "This is a notification.",
    Duration = 5,
    Image = "rbxassetid://10734953451"
})
```

### Notification Properties

| Property   | Type   | Description         |
| ---------- | ------ | ------------------- |
| `Title`    | string | Notification title  |
| `Content`  | string | Message text        |
| `Duration` | number | Time in seconds     |
| `Image`    | string | Optional icon image |

---

## 💬 Dialogs

```lua
Window:Dialog({
    Title = "Confirmation",
    Content = "Do you want to continue?",
    Options = {
        { Name = "Cancel" },
        {
            Name = "Confirm",
            Callback = function()
                print("Confirmed")
            end
        }
    }
})
```

---

## ⚙️ UI Elements (Options API)

All UI elements are created inside **Tabs**.

---

### Section

```lua
MainTab:AddSection("General Settings")
```

---

### Toggle

```lua
MainTab:AddToggle({
    Name = "Enable Feature",
    Default = false,
    Callback = function(Value)
        print(Value)
    end
})
```

---

### Button

```lua
MainTab:AddButton({
    Name = "Run Action",
    Debounce = 0.5,
    Callback = function()
        print("Button clicked")
    end
})
```

---

### Slider

```lua
MainTab:AddSlider({
    Name = "Speed",
    Min = 0,
    Max = 100,
    Increment = 1,
    Default = 50,
    Callback = function(Value)
        print(Value)
    end
})
```

---

### Dropdown

```lua
MainTab:AddDropdown({
    Name = "Select Mode",
    Options = { "Easy", "Normal", "Hard" },
    Default = "Normal",
    Callback = function(Value)
        print(Value)
    end
})
```

#### Multi-Select Dropdown

```lua
MainTab:AddDropdown({
    Name = "Select Items",
    MultiSelect = true,
    Options = { "Sword", "Gun", "Bow" },
    Default = { "Sword" },
    Callback = function(Value)
        print(Value)
    end
})
```

---

### TextBox

```lua
MainTab:AddTextBox({
    Name = "Player Name",
    Placeholder = "Enter text...",
    ClearOnFocus = true,
    Callback = function(Text)
        print(Text)
    end
})
```

---

### Paragraph

```lua
MainTab:AddParagraph(
    "Information",
    "This is a paragraph.\nSecond line of text."
)
```

---

## 🔗 Discord Invite

```lua
MainTab:AddDiscordInvite({
    Title = "Redz Hub Community",
    Description = "Official Redz Hub community server.",
    Banner = "rbxassetid://17382040552",
    Logo = "rbxassetid://17382040552",
    Invite = "https://discord.gg/redz-hub",
    Members = 470000,
    Online = 20000
})
```

---

## 💾 Flags (Persistent State)

Flags allow saving and restoring option values.

```lua
MainTab:AddToggle({
    Name = "Auto Farm",
    Flag = "auto_farm"
})
```

```lua
local SavedValue = Window:GetFlag("auto_farm") or false

MainTab:AddToggle({
    Name = "Auto Farm",
    Default = SavedValue,
    Callback = function(Value)
        Window:SetFlag("auto_farm", Value)
    end
})
```

---

## 🔍 UI Scale

### Scale Limits

* Minimum: `0.6`
* Maximum: `1.6`
* Default: `1.0`

### Set UI Scale

```lua
Library:SetUIScale(1.0)
```

---

## 🧪 Full Example

```lua
local Library = loadstring(game:HttpGet("URL"))()

local Window = Library:MakeWindow({
    Title = "Example Hub",
    SubTitle = "Redz Interface V5",
    SaveFolder = "ExampleHub"
})

local Tab = Window:MakeTab({ "Main", "Home" })

Tab:AddToggle({
    Name = "Example Toggle",
    Callback = function(Value)
        print(Value)
    end
})

Library:SetTheme("Darker")
```


Só falar 💅
