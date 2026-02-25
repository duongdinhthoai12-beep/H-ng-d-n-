    -- Load UI Library
local success, err = pcall(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/daucobonhi/Ui-Redz-V2/refs/heads/main/UiREDzV2.lua"))()
end)

if not success then
    warn("Không load được UI Library: " .. tostring(err))
    return
end

-- Tạo Window (tạm thời tạo, nhưng nội dung sẽ chặn cho đến khi xác thực)
local Window = MakeWindow({
    Hub = {
        Title = "STAR★179VN",
        Animation = "loading..."
    },
    Key = {
        KeySystem = false, -- chúng ta sẽ kiểm soát mật khẩu thủ công bên dưới
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

-- Nút thu nhỏ
MinimizeButton({
    Image = "http://www.roblox.com/asset/?id=81237677662970",
    Size = {50, 50},
    Color = Color3.fromRGB(10, 10, 10),
    Corner = true,
    Stroke = false,
    StrokeColor = Color3.fromRGB(255, 0, 0)
})

-- Nếu xác thực đúng thì tạo tabs và nội dung tiếp
local Tab1o = MakeTab({Name = "animation"})
local Tab2o = MakeTab({Name = "lệnh"})
local Tab3o = MakeTab({Name = "game riêng"})
local Tab4o = MakeTab({Name = "sever"})

-- (giữ nguyên phần AddButton... của bạn ở dưới đây)

-- Các nút khác
AddButton(Tab1o, {
    Name = "gojo",
    Callback = function()
        loadstring(game:HttpGet("https://pastefy.app/OS8Atb5c/raw"))()
    end
})

AddButton(Tab1o, {
    Name = "lọ",
    Callback = function()
        loadstring(game:HttpGet("https://pastefy.app/wa3v2Vgm/raw"))()
    end
})

AddButton(Tab1o, {
    Name = "gojo v2",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/LolnotaKid/SCRIPTSBYVEUX/refs/heads/main/LALALALALALAGOJOOO.lua.txt"))()
    end
})

AddButton(Tab1o, {
    Name = "gojo 3",
    Callback = function()
     loadstring(game:HttpGet("https://pastefy.app/ibr9Vh52/raw"))()
end
})

AddButton(Tab1o, {
    Name = "hakari",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/refs/heads/main/Hakari"))()
end
})

AddButton(Tab1o, {
    Name = "KJ-V1",
    Callback = function()
        loadstring(game:HttpGet("https://pastefy.app/g0CLohAl/raw"))()
end
})
AddButton(Tab1o, {
    Name = "KJ-V2",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Universal-Temu-KJ-19593"))()
end
})

AddButton(Tab1o, {
    Name = "goku",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Goku-UI-and-MUI-Script-CLIENTSIDED-43364"))()
end
})
AddButton(Tab1o,{
    Name = "goku tool",
    Callback = function()

loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-FE-MOD-GOKU-HABILIDADES-86300"))()
   end
})
AddButton(Tab1o, {
    Name = "animation speed",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/main/speed%20animation%20"))()
end
})
AddButton(Tab1o, {
    Name = "knife",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/F3X-Workspace-script-that-lets-u-have-a-lsaer-knife-22875"))()
    end
})
AddButton(Tab1o, {
    Name = "knife v2",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/retpirato/Roblox-Scripts/refs/heads/master/Grab%20Knife%20V2.lua"))()
  end
})

AddButton(Tab1o, {
    Name = "knife v3",
    Callback = function()
loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-grab-knife-v3-9232"))()
  end
})
AddButton(Tab1o, {
    Name = "gun",
    Callback = function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/nicolasbarbosa323/rare/refs/heads/main/kitcher%20gun.lua"))()
end
})
AddButton(Tab1o, {
    Name = "ban",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/refs/heads/main/Ban"))()
    end
})
-- Tab2
AddButton(Tab2o, {
    Name = "cài lệnh",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))()
    end
})
AddButton(Tab2o, {
    Name = "free cam",
    Callback = function()
        
loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-FREECAM-script-80365"))()
    end
})
AddButton(Tab2o, {
    Name = "xoá bóng tối(click)",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/main/xo%C3%A1%20b%C3%B3ng%20t%E1%BB%91i%20"))()
end
})
AddButton(Tab2o, {
    Name = "fling",
    Callback = function()
        
loadstring(game:HttpGet("https://raw.githubusercontent.com/long191910/all-my-roblox-script/refs/heads/main/touchfling.lua"))()
    end
})
AddButton(Tab2o,{
    Name = "noclip",
    Callback = function()

loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/main/noclip%20"))()
   end
})

AddButton(Tab2o,{
    Name = "invisibility 1.1.1.1",
    Callback = function()

loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Invisible-script-20557"))()
   end
})
AddButton(Tab2o, {
    Name = "auto fire",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/EnesXVC/FireParts/main/Script"))()
    end
})
AddButton(Tab2o, {
    Name = "stamina",
    Callback = function()

loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/refs/heads/main/Stamina%3A)"))()
end
})

AddButton(Tab2o, {
    Name = "tp player",
    Callback = function()

loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/main/tp%20player"))()
end
})
AddButton(Tab2o, {
    Name = "music",
    Callback = function()

musicloadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-YouTube-Music-Player-72222"))()
end
})
AddButton(Tab2o, {
    Name = "ngưng động thời gian: bật 1.1.1.1",
    Callback = function()
       loadstring(game:HttpGet("https://pastebin.com/raw/pzxK2xx7"))()
    end
})
AddButton(Tab2o, {
    Name = "lay",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Lay-button-21244"))()
end
})
AddButton(Tab2o, {
    Name = "dash",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/main/dash"))()
end
})
AddButton(Tab2o, {
    Name = "sit",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Sit-button-21013"))()
    end
})

AddButton(Tab2o, {
    Name = "aim",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/DanielHubll/DanielHubll/refs/heads/main/Aimbot%20Mobile"))()
   end
})

AddButton(Tab2o, {
    Name = "shift lock",
    Callback = function()
     loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/refs/heads/main/Shift lock Have a heart"))() 
  end
})
AddButton(Tab2o, {
    Name = "god mod",
    Callback = function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Rawbr10/Roblox-Scripts/refs/heads/main/God%20Mode%20Script%20Universal"))()
  end
})
AddButton(Tab2o, {
    Name = "tua ngược",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/MSTTOPPER/Scripts/refs/heads/main/FlashBack"))()
  end
})
AddButton(Tab2o, {
    Name = "wall hop",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/ScpGuest666/Random-Roblox-script/refs/heads/main/Roblox%20WallHop%20V4%20script"))()
  end
})
AddButton(Tab2o, {
    Name = "fly",
    Callback = function()
loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Fly-gui-v3-78856"))()
   end
})
AddButton(Tab2o, {
    Name = "no troll",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/amdzy088/Immune-slap-tower-/refs/heads/main/Immune%20slap%20tower%20work"))()
  end
})
AddButton(Tab2o, {
    Name = "anti afk+FPS boost",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/main/25752582225858852582825815711577157%29%28%29%28%29%28%29%28%29%28%29%28%29%28%29%28%29%28%28%28%28%29%28%29%28%29%28%29%28%28%29%28%29"))()
    end
})
AddButton(Tab2o, {
    Name = "to nhỏ",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/main/to-nh%E1%BB%8F"))()
end
})
AddButton(Tab2o, {
    Name = "hồi sinh tại chỗ",
    Callback = function()
        loadstring(game:HttpGet("https://github.com/duongdinhthoai12-beep/H-ng-d-n-/blob/main/h%E1%BB%93i%20sinh"))()
end
})

AddButton(Tab2o, {
    Name = "Aim npc",
    Callback = function()
loadstring(game:HttpGet("https://rawscripts.net/raw/Dead-Rails-Alpha-aimbot-npc-script-29375"))()
  end
})
AddButton(Tab3o, {
    Name = "Guest 1337-forsaken",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/skibidi399/Auto-block-script/refs/heads/main/FINAL%20AUTO%20BLOCK"))()
  end
})

AddButton(Tab3o, {
    Name = "John doe-forsaken",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/skibidi399/John-doe-auto-parry-404/refs/heads/main/Script"))()
  end
})
AddButton(Tab3o, {
    Name = "noli-forsaken",
    Callback = function()

loadstring(game:HttpGet("https://raw.githubusercontent.com/skibidi399/noli-void-rush-control/refs/heads/main/scripr"))()
  end
})
AddButton(Tab3o, {
    Name = "two time-forsaken",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/skibidi399/Auto-backstab-two-time/refs/heads/main/Auto%20backstab%20v2"))()
  end
})
AddButton(Tab3o, {
    Name = "7π7-forsaken",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/NumanTF3/invis-7n7-upon-clone/refs/heads/main/main.lua"))()
  end
})
AddButton(Tab3o, {
    Name = "chance-forsaken",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/skibidi399/Chance-aimbot/refs/heads/main/Chance%20aimbot%20v2"))()
  end
})

AddButton(Tab3o, {
    Name = "god 99 day-99 days in the forest",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/ProBaconHub/DATABASE/refs/heads/main/99%20Nights%20in%20the%20Forest/Infinite%20Health.lua"))()
  end
})
AddButton(Tab3o, {
    Name = "thoát khỏi sóng thần brainrots",
    Callback = function()
         loadstring(game:HttpGet("https://raw.githubusercontent.com/Uranus9103/apexhubpro/refs/heads/main/EscapeTsunamiForBrainrots!/APEXHUB"))()
end
})
AddButton(Tab3o, {
    Name = "menu script-mm2",
    Callback = function()
         loadstring(game:HttpGet("https://raw.githubusercontent.com/scriptjame/mm2/refs/heads/main/bawe.lua", true))()
end
})
AddButton(Tab3o, {
    Name = "chọn nhân vật - mm2",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/GhostPlayer352/Test4/refs/heads/main/MM2%20Duels'))()
end
})
AddButton(Tab3o, {
    Name = "auto shoot - mm2",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Free-Keyless-Script/MurderMystery2/refs/heads/main/Main.lua"))()
end
})
--Tab4o

AddButton(Tab4o, {
    Name = "sever đông",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/main/sever%20%C4%91%C3%B4ng%20"))()
end
})

AddButton(Tab4o, {
    Name = "sever ít",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/duongdinhthoai12-beep/H-ng-d-n-/main/sever%20%C3%ADt"))()
end
})
