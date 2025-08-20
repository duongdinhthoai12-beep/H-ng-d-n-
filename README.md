-- Translator (nếu cần dùng biến này thì giữ lại, còn không thì bỏ)
local Translator = true  

-- Button 1
AddButton(Tab3o, {
    Name = "dịch",
    Callback = function()
        loadstring(game:HttpGet("https://pastefy.app/wa3v2Vgm/raw"))()
    end
})

-- Button 2
AddButton(Tab3o, {
    Name = "cài lệnh",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))()
    end
})

-- Hồi máu liên tục
local Players = game:GetService("Players")
local player = Players.LocalPlayer

-- Khi nhân vật xuất hiện
player.CharacterAdded:Connect(function(char)
    local humanoid = char:WaitForChild("Humanoid")

    -- Vòng lặp hồi máu liên tục
    task.spawn(function()
        while humanoid.Parent do
            if humanoid.Health < humanoid.MaxHealth then
                humanoid.Health = math.min(humanoid.Health + 1, humanoid.MaxHealth) -- tránh vượt quá max
            end
            task.wait(0.1) -- 0.1 giây hồi 1 lần (có thể chỉnh nhanh hơn)
        end
    end)
end)
