loadstring(game:HttpGet("https://raw.githubusercontent.com/daucobonhi/Ui-Redz-V2/refs/heads/main/UiREDzV2.lua"))()

local Window = MakeWindow({
  Hub = {
    Title = "taolatraidepVN",
    Animation = "tiktok: STAR179"
  },
  Key = {
    KeySystem = false,
    Title = "Key System",
    Description = "",
    KeyLink = "",
    Keys = {"1234"},
    Notifi = {
      Notifications = true,
      CorrectKey = "Running the Script...",
      IncorrectKey = "The key is incorrect",
      CopyKeyLink = "Copied to Clipboard"
    }
  }
})

MinimizeButton({
  Image = "http://www.roblox.com/asset/?id=112692420860781",
  Size = {60, 60},
  Color = Color3.fromRGB(10, 10, 10),
  Corner = true,
  Stroke = false,
  StrokeColor = Color3.fromRGB(255, 0, 0)
})

-- Tabs
local Tab1o = MakeTab({Name = "animation"})
local Tab2o = MakeTab({Name = "cài lệnh"})
local Tab3o = MakeTab({Name = "extra"})

-- Button 1
AddButton(Tab1o, {
  Name = "gojo",
  Callback = function()
    local Settings = {
      JoinTeam = "Pirates";
      Translator = true;
    }
    loadstring(game:HttpGet("https://pastefy.app/OS8Atb5c/raw"))()
  end
})

-- Button 2
AddButton(Tab2o, {
  Name = "lọ vương",
  Callback = function()
    local Settings = {
      JoinTeam = "Pirates";
      Translator = true;
    }
    loadstring(game:HttpGet("https://pastefy.app/wa3v2Vgm/raw"))()
  end
})

-- Button 3
AddButton(Tab3o, {
  Name = "cài lệnh",
  Callback = function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))()
  end
})

-- Button 4: Bất tử ON/OFF
AddButton(Tab3o, {
  Name = "Bật/Tắt bất tử",
  Callback = function()
      local Players = game:GetService("Players")
      local player = Players.LocalPlayer
      local character = player.Character or player.CharacterAdded:Wait()
      local humanoid = character:WaitForChild("Humanoid")

      if humanoid:FindFirstChild("GodMode") then
          -- Tắt bất tử
          humanoid.GodMode:Destroy()
          warn("❌ Bất tử OFF")
      else
          -- Bật bất tử
          local god = Instance.new("BoolValue")
          god.Name = "GodMode"
          god.Parent = humanoid

          humanoid:GetPropertyChangedSignal("Health"):Connect(function()
              if god.Parent and god.Value ~= false then
                  if humanoid.Health < humanoid.MaxHealth then
                      humanoid.Health = humanoid.MaxHealth
                  end
              end
          end)

          warn("✅ Bất tử ON")
      end
  end
})
