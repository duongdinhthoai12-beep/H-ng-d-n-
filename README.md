--[[
📦 TÊN CÔNG CỤ: AFK + FPS Boost UI

📌 TÍNH NĂNG CHÍNH:
+ Tự động hoạt động để tránh bị kick khi AFK
+ Hiển thị FPS (khung hình/giây) và thời gian AFK
+ Bật/tắt chế độ giảm đồ họa giúp tăng FPS (hạn chế lag)
+ Ẩn/hiện giao diện bằng phím [V] (PC) hoặc nút 👁️ (Mobile)
+ Thiết kế giao diện đẹp, hiện đại và có thể kéo thả

📘 CÁCH DÙNG:
1. Dán đoạn mã này vào LocalScript (Client)
2. Giao diện sẽ hiện ngay trong game
3. Nhấn nút "Bật FPS Boost" để giảm đồ họa tối đa
4. Nhấn "V" hoặc biểu tượng 👁️ để ẩn/hiện giao diện
5. Nhấn ✕ để tắt giao diện hoàn toàn
]

local plr = game:GetService("Players").LocalPlayer
local cam = workspace.CurrentCamera
local vu = game:GetService("VirtualUser")
local rs = game:GetService("RunService")
local uis = game:GetService("UserInputService")
local gui = Instance.new("ScreenGui", plr:WaitForChild("PlayerGui"))

-- Nút ẩn/hiện dành cho mobile (hình con mắt)
local toggleButton = Instance.new("ImageButton", gui)
toggleButton.Size = UDim2.new(0, 40, 0, 40)
toggleButton.Position = UDim2.new(1, -50, 1, -50) -- Góc dưới bên phải
toggleButton.Image = "rbxassetid://6034287594" -- Eye-slash (ẩn) -- icon hình con mắt 👁️
toggleButton.BackgroundTransparency = 1

-- Chống kick khi AFK
plr.Idled:Connect(function()
    vu:Button2Down(Vector2.new(), cam.CFrame)
    wait(0.5)
    vu:Button2Up(Vector2.new(), cam.CFrame)
end)

-- Tạo UI
local f = Instance.new("Frame", gui)
f.Size = UDim2.new(0, 220, 0, 210)
f.Position = UDim2.new(0, 25, 0, 25)
f.BackgroundColor3 = Color3.fromRGB(30,30,30)
f.Active = true f.Draggable = true
-- 🌈 Rainbow Border
local stroke = Instance.new("UIStroke", f)
stroke.Thickness = 2

task.spawn(function()
    while true do
        for i = 0, 1, 0.01 do
            stroke.Color = Color3.fromHSV(i, 1, 1)
            task.wait(0.03)
        end
    end
end)
Instance.new("UICorner", f).CornerRadius = UDim.new(0, 10)

local title = Instance.new("TextLabel", f)
title.Size = UDim2.new(1, -30, 0, 25)
title.Position = UDim2.new(0, 10, 0, 5)
title.Text = "💸 Auto"
title.Font = Enum.Font.GothamBold
title.TextScaled = true
title.BackgroundTransparency = 1
title.TextColor3 = Color3.new(1,1,1)
title.TextXAlignment = Enum.TextXAlignment.Left

local close = Instance.new("TextButton", f)
close.Size = UDim2.new(0, 25, 0, 25)
close.Position = UDim2.new(1, -30, 0, 5)
close.Text = "✕"
close.BackgroundColor3 = Color3.fromRGB(200,60,60)
Instance.new("UICorner", close)
close.MouseButton1Click:Connect(function() f:Destroy() end)

local timer = Instance.new("TextLabel", f)
timer.Position = UDim2.new(0, 10, 0, 40)
timer.Size = UDim2.new(1, -20, 0, 25)
timer.Text = "AFK: 300s"
timer.BackgroundColor3 = Color3.fromRGB(40,40,45)
timer.TextColor3 = Color3.new(1,1,1)
timer.Font = Enum.Font.Gotham
timer.TextScaled = true
Instance.new("UICorner", timer)

-- Ghi chú cho timer
local afkNote = Instance.new("TextLabel", f)
afkNote.Position = UDim2.new(0, 10, 0, 65)
afkNote.Size = UDim2.new(1, -20, 0, 15)
afkNote.Text = "⏳ Đếm ngược đến lần tiếp theo nhân vật sẽ tự hoạt động để tránh bị kick khỏi game."
afkNote.TextColor3 = Color3.fromRGB(255, 255, 160)
afkNote.BackgroundTransparency = 1
afkNote.Font = Enum.Font.GothamBold
afkNote.TextScaled = true
afkNote.TextSize = 20
afkNote.TextWrapped = true

local totalTime = Instance.new("TextLabel", f)
totalTime.Position = UDim2.new(0, 10, 0, 85)
totalTime.Size = UDim2.new(1, -20, 0, 20)
totalTime.Text = "🕒 Tổng thời gian AFK: 0 phút"
totalTime.BackgroundTransparency = 1
totalTime.TextColor3 = Color3.fromRGB(180, 180, 180)
totalTime.Font = Enum.Font.GothamSemibold
totalTime.TextScaled = true

local fps = Instance.new("TextLabel", f)
fps.Position = UDim2.new(0, 10, 0, 110)
fps.Size = UDim2.new(1, -20, 0, 25)
fps.Text = "FPS: 0"
fps.BackgroundColor3 = Color3.fromRGB(40,40,45)
fps.TextColor3 = Color3.fromRGB(100,255,100)
fps.Font = Enum.Font.Gotham
fps.TextScaled = true
Instance.new("UICorner", fps)

local toggle = Instance.new("TextButton", f)
toggle.Position = UDim2.new(0, 10, 0, 140)
toggle.Size = UDim2.new(1, -20, 0, 25)
toggle.Text = "🟢 Bật FPS Boost"
toggle.BackgroundColor3 = Color3.fromRGB(50,120,50)
toggle.Font = Enum.Font.GothamBold
toggle.TextScaled = true
toggle.TextColor3 = Color3.new(1,1,1)
Instance.new("UICorner", toggle)

-- Ghi chú
local note = Instance.new("TextLabel", f)
note.Position = UDim2.new(0, 10, 0, 170)
note.Size = UDim2.new(1, -20, 0, 25)
note.Text = "👁️ Nhấn [V] trên PC hoặc icon 👁️ (mobile) để ẩn/hiện UI — ✕ để tắt giao diện"
note.TextColor3 = Color3.fromRGB(200, 200, 200)
note.BackgroundTransparency = 1
note.Font = Enum.Font.GothamSemibold
note.TextScaled = true
note.TextWrapped = true

-- FPS Counter
-- FPS Counter + đổi màu + viền theo FPS
local count, last = 0, os.clock()

rs.RenderStepped:Connect(function()
    count += 1
    if os.clock() - last >= 1 then
        fps.Text = "FPS: " .. count

        -- 🎨 Đổi màu chữ theo FPS
        if count <= 10 then
            fps.TextColor3 = Color3.fromRGB(255,60,60) -- đỏ
            stroke.Color = Color3.fromRGB(255,60,60)
        elseif count <= 30 then
            fps.TextColor3 = Color3.fromRGB(255,200,0) -- vàng
            stroke.Color = Color3.fromRGB(255,200,0)
        else
            fps.TextColor3 = Color3.fromRGB(100,255,100) -- xanh
            stroke.Color = Color3.fromRGB(100,255,100)
        end

        count = 0
        last = os.clock()
    end
end)
-- Boost đồ họa
local function boost()
    local Lighting = game:GetService("Lighting")
    settings().Rendering.QualityLevel = Enum.QualityLevel.Level01
    Lighting.GlobalShadows = false
    Lighting.Brightness = 0
    Lighting.FogEnd = 1e9
    for _,v in ipairs(workspace:GetDescendants()) do
        if v:IsA("Decal") or v:IsA("Texture") or v:IsA("Sound") then pcall(function() v:Destroy() end) end
        if v:IsA("ParticleEmitter") or v:Is-- FPS Counter + đổi màu
local count, last = 0, os.clock()

rs.RenderStepped:Connect(function()
    count += 1
    if os.clock() - last >= 1 then
        fps.Text = "FPS: " .. count

        -- 🎨 Đổi màu theo FPS
        if count <= 10 then
            fps.TextColor3 = Color3.fromRGB(255, 60, 60) -- 🔴 Đỏ
        elseif count <= 30 then
            fps.TextColor3 = Color3.fromRGB(255, 200, 0) -- 🟡 Vàng
        else
            fps.TextColor3 = Color3.fromRGB(100, 255, 100) -- 🟢 Xanh
        end

        count = 0
        last = os.clock()
    end
end)A("Trail") or v:IsA("Beam") then v.Enabled = false end
        if v:IsA("BasePart") then
            v.Material = Enum.Material.SmoothPlastic
            v.Reflectance = 0
            v.CastShadow = false
        end
    end
end

local function unboost()
    local Lighting = game:GetService("Lighting")
    Lighting.GlobalShadows = true
    Lighting.Brightness = 2
    Lighting.FogEnd = 1000
end

-- Toggle FPS Boost
local boosted = false
toggle.MouseButton1Click:Connect(function()
    if not boosted then
        boost()
        toggle.Text = "🔴 Đang bật"
        toggle.BackgroundColor3 = Color3.fromRGB(150,60,60)
    else
        unboost()
        toggle.Text = "🟢 Bật FPS Boost"
        toggle.BackgroundColor3 = Color3.fromRGB(50,120,50)
    end
    boosted = not boosted
end)

-- Ẩn/hiện UI bằng phím V hoặc icon trên mobile
local function toggleUI()
    f.Visible = not f.Visible
end

toggleButton.MouseButton1Click:Connect(toggleUI)
uis.InputBegan:Connect(function(input, g)
    if not g and input.UserInputType == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.V then
        toggleUI()
    end
end)

-- AFK Timer + Tổng thời gian treo
local totalMinutes = 0
spawn(function()
    while true do
        local t = math.random(280, 320)
        for i = t, 0, -1 do
            if f.Visible then
                timer.Text = "AFK: "..i.."s"
                totalTime.Text = "Tổng thời gian treo: " .. tostring(totalMinutes) .. " phút"
            end
            wait(1)
        end
        totalMinutes += math.floor(t / 60)
        cam.CFrame *= CFrame.Angles(0, math.rad(math.random(3, 6)), 0)
        vu:Button2Down(Vector2.new(), cam.CFrame)
        wait(math.random(0.4, 0.8))
        vu:Button2Up(Vector2.new(), cam.CFrame)
    end
end)
