# Zen-Zest-UILibrary-V2
Zen Zest UILibrary V2 Isn't A Remake But A New UI Library.
- Prototype.

## Features

Window Or Library:
```Luau
--[[
Library:Destroy()
Library:Visible(true) - Boolean (true Or false)
Library:AddTheme("Hello"{
-- Blah Blah Check The Source.
})
Library:SetTheme("Hello")
Library:GetTheme("Hello")
Library:SetFont("Ubuntu")
]]
```

Button:
```Luau
- Destroy()
- SetLocked()
- SetTitle()
- SetDesc() or SetDescription()

--[[
Destroy() can be used as Button:Destroy()
SetLocked() - Boolean (false Or true)
SetTitle() - String (Text Or Numbers Or Both Inside A "" Or '')
SetDesc() or SetDescription() - Both Are Strings (Text Or Numbers Or Both Inside A "" Or '')
]]
```

Toggle:
```Luau
- Destroy()
- SetLocked()
- SetTitle()
- SetDesc() or SetDescription()
- SetDefault()
- State()

--[[
Destroy() can be used as Button:Destroy()
SetLocked() - Boolean (false Or true)
SetTitle() - String (Text Or Numbers Or Both Inside A "" Or '')
SetDesc() or SetDescription() - Both Are Strings (Text Or Numbers Or Both Inside A "" Or '')
SetDefault() - Boolean (false Or true)
State() - Function (Returns true Or false)
]]
```

## Usage Example
```Luau
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/TheLostStar7/Zen-Zest-UILibrary-V2/refs/heads/main/Main"))()
local win = Library:CreateWindow({
    Window = {
        Title = "Wsp",
        Scale_Settings = {
            Auto_Scale = true,
            Scale = {Desktop = 1,Mobile = 1.1}
        }
    },
    Settings = {
        Theme_Settings = {
            Theme = "Red",
            Rainbow = false,
            Rainbow_Method = "Gradient", -- Rbg or Gradient.
            Rainbow_Speed = 3 -- default is 5.
        },
        Keybind = "Z",
        Font = "Ubuntu"
    }
})

local first = win:AddTab({Title = "Main Tab",Opened = true})
local second = win:AddTab({Title = "Misc Tab",Opened = false})

first:AddButton({Title = "Hello",Description = "Blah Blah Blah",Callback = function(self)
    print("Hello!")
    self:SetLocked(true)
    self:SetTitle("Hello [Locked]")
end,})
first:AddButton({Title = "Expand On This Button",Callback = function(self)
    self:SetDesc("Hell0 World.")
end,})
first:AddButton({Title = "Locked Button",Desc = "You can't click me",Locked = true,Callback = function()
    print("This shouldn't run!")
end,})
first:AddButton({Title = "Destroy",Desc = "Destroy The UILibrary:>",Callback = function()
    Library:Destroy()
end,})
first:AddToggle({Title = "Lol",Desc = "You can't click me?",Locked = false,Default = true,Callback = function(status)
    print(status)
end,})
local tgl;tgl = first:AddToggle({Title = "Lol V2",Desc = "You can't click me!!!",Locked = false,Default = false,Callback = function(status)
    print("Nuh uh:",status)
end,})
first:AddButton({Title = "Turn On Lol V2",Callback = function()
    tgl:SetDefault(tgl:State())
end,})
```
