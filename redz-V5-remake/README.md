# ✨ Wand UI

### Redz Library V5 • Remake

## 📖 Sobre

**Wand UI** é uma versão reconstruída e otimizada da **Redz Library V5**, mantendo o visual original com melhorias de desempenho, organização e usabilidade.

O nome **Wand** representa a próxima geração das UIs do **Redz Hub**.

**Características**

* Open-Source
* Leve e otimizada
* Design fiel à Redz V5
* Feita para scripts do **Redz Hub**

**Autor:** `real_redz`

---

## 🚀 Instalação

```lua
local Library = loadstring(game:HttpGet(
  "https://raw.githubusercontent.com/azur-fnf/redz-interface/refs/heads/main/redz-V5-remake/main.luau"
))()
```

---

## 🪟 Criando uma Janela

```lua
local Window = Library:MakeWindow({
  Title = "Nice Hub : Cool Game",
  SubTitle = "dev by real_redz",
  ScriptFolder = "redz-library-V5"
})
```

---

## 🧭 API da Window

### Métodos Principais

* `MakeTab(Configs)`
* `Notify(Configs)`
* `Dialog(Configs)`
* `SelectTab(Tab | number)`
* `SetTitle(string)`
* `SetSubTitle(string)`
* `GetTitle()`
* `GetSubTitle()`
* `Destroy()`

### UI & Tema

* `SetUIScale(number)`
* `GetMinScale()`
* `GetMaxScale()`
* `SetTheme(string)`
* `GetTheme()`
* `GetThemes()`
* `IsValidTheme(string)`

### Flags

* `SetFlag(string, any)`
* `GetFlag(string)`
* `DeleteFlags()`

---

## 📦 Minimizer

```lua
local Minimizer = Window:NewMinimizer({
  KeyCode = Enum.KeyCode.LeftControl
})

Minimizer:CreateMobileMinimizer({
  Image = "rbxassetid://0",
  BackgroundColor3 = Color3.fromRGB(0, 0, 0)
})
```

---

## 📑 Tabs

### Normal

```lua
local Tab = Window:MakeTab({
  Title = "Cool Tab",
  Icon = "Home"
})
```

### Compacto

```lua
local Tab = Window:MakeTab({ "Cool Tab", "Home" })
```

---

## 🔔 Notificações

```lua
Window:Notify({
  Title = "Notification",
  Content = "this is a Notification",
  Image = "rbxassetid://10734953451",
  Duration = 5
})
```

---

## 💬 Dialog

```lua
Window:Dialog({
  Title = "Hello!",
  Content = "do you like Coffee?",
  Options = {
    { Name = "No" },
    {
      Name = "Yes!",
      Callback = function()
        print("Yes, i like Coffee")
      end
    }
  }
})
```

---

## ⚙️ Options API

### Propriedades Comuns

* `SetTitle(string)`
* `SetDescription(string)`
* `SetVisible(boolean)`
* `Destroy()`
* `AddCallback(function)`

---

## 🧩 Criando Opções

### Section

```lua
Tab:AddSection("Section")
```

### Toggle

```lua
Tab:AddToggle({
  Name = "Toggle",
  Default = false,
  Callback = function(Value)
    
  end
})
```

### Button

```lua
Tab:AddButton({
  Name = "My Button",
  Debounce = 0.5,
  Callback = function()
    
  end
})
```

### Slider

```lua
Tab:AddSlider({
  Name = "Cool Title",
  Min = -5,
  Max = 5,
  Increment = 0.25,
  Default = 0,
  Callback = function(Value)
    
  end
})
```

### Dropdown

```lua
Tab:AddDropdown({
  Name = "Dropdown",
  Options = {"one", "two", "three"},
  Default = "one",
  Callback = function(Value)
    
  end
})
```

#### Multi-Select

```lua
Tab:AddDropdown({
  Name = "Dropdown",
  MultiSelect = true,
  Options = {"one", "two", "three"},
  Default = {"one"},
  Callback = function(Value)
    
  end
})
```

### TextBox

```lua
Tab:AddTextBox({
  Name = "My TextBox",
  Placeholder = "input text...",
  ClearOnFocus = true,
  Callback = function(Value)
    
  end
})
```

### Paragraph

```lua
Tab:AddParagraph("Paragraph", "This is a Paragraph\nSecond Line")
```

---

## 💙 Discord Invite

```lua
Tab:AddDiscordInvite({
  Title = "redz Hub | Community",
  Description = "Official community for redz Hub users.",
  Banner = "rbxassetid://17382040552",
  Logo = "rbxassetid://17382040552",
  Invite = "https://discord.gg/redz-hub",
  Members = 470000,
  Online = 20000
})
```

---

## 🔍 Flags (Estado Persistente)

```lua
Tab:AddToggle({
  Name = "Cool Toggle",
  Flag = "toggle_flag"
})
```

```lua
local Value = Window:GetFlag("toggle_flag") or false

Tab:AddToggle({
  Name = "Cool Toggle",
  Default = Value,
  Callback = function(v)
    Window:SetFlag("toggle_flag", v)
  end
})
```

---

## 🔎 Escala da UI

* **Min:** `0.6`
* **Max:** `1.6`
* **Padrão:** `1.0`

```lua
Library:SetUIScale(1.0)
```


Só mandar 💅
