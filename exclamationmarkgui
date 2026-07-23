- SERVICES
local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local LocalPlayer = Players.LocalPlayer

-- GUI SETUP
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "ExclamationMarkGui"
screenGui.ResetOnSpawn = false
screenGui.IgnoreGuiInset = true
screenGui.Parent = game.CoreGui

-- RE-ADD GUI AFTER RESPAWN
LocalPlayer.CharacterAdded:Connect(function()
    if not screenGui.Parent then
        screenGui.Parent = game.CoreGui
    end
end)

-- Main GUI Frame
local mainFrame = Instance.new("Frame", screenGui)
mainFrame.Size = UDim2.new(0, 400, 0, 300)
mainFrame.Position = UDim2.new(0.5, -200, 0.5, -150)
mainFrame.BackgroundColor3 = Color3.fromRGB(250, 246, 240)
mainFrame.BorderSizePixel = 0
-- Botón flotante para abrir de nuevo (limpio y aesthetic)
local toggleButton = Instance.new("TextButton", screenGui)
toggleButton.Size = UDim2.new(0, 42, 0, 42)
toggleButton.Position = UDim2.new(0, 20, 0.5, -21)
toggleButton.BackgroundColor3 = Color3.fromRGB(253, 250, 243)
toggleButton.Font = Enum.Font.Bodoni
toggleButton.TextSize = 24
toggleButton.Text = "♡"
toggleButton.AutoButtonColor = false
toggleButton.Visible = false
toggleButton.BorderSizePixel = 0 -- Sin bordes feos cuadrados

local toggleCorner = Instance.new("UICorner", toggleButton)
toggleCorner.CornerRadius = UDim.new(1, 0) -- Círculo perfecto

local toggleStroke = Instance.new("UIStroke", toggleButton)
toggleStroke.Thickness = 2
toggleStroke.Color = Color3.fromRGB(0, 0, 255)

local toggleCorner = Instance.new("UICorner", toggleButton)
toggleCorner.CornerRadius = UDim.new(1, 0)

-- Esquinas redondas + Borde
local corner = Instance.new("UICorner", mainFrame)
corner.CornerRadius = UDim.new(0, 12)

local borderStroke = Instance.new("UIStroke", mainFrame)
borderStroke.Thickness = 3
borderStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border

-- Rainbow Title
local rainbowLabel = Instance.new("TextLabel", mainFrame)
rainbowLabel.Size = UDim2.new(1, 0, 0, 50)
rainbowLabel.Position = UDim2.new(0, 0, 0, 0)
rainbowLabel.BackgroundTransparency = 1
rainbowLabel.Text = "<i>exclamationmark gui v2</i>"
rainbowLabel.RichText = true
rainbowLabel.Font = Enum.Font.Bodoni
rainbowLabel.TextSize = 36
rainbowLabel.TextStrokeTransparency = 0.7
rainbowLabel.TextColor3 = Color3.new(1, 0, 0)


-- Drag support for mainFrame
do
    local dragging, dragInput, dragStart, startPos
    local function update(input)
        local delta = input.Position - dragStart
        mainFrame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X,
                                       startPos.Y.Scale, startPos.Y.Offset + delta.Y)
    end
    mainFrame.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1
        or input.UserInputType == Enum.UserInputType.Touch then
            dragging = true
            dragStart = input.Position
            startPos = mainFrame.Position
            input.Changed:Connect(function()
                if input.UserInputState == Enum.UserInputState.End then
                    dragging = false
                end
            end)
        end
    end)
    mainFrame.InputChanged:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseMovement
        or input.UserInputType == Enum.UserInputType.Touch then
            dragInput = input
        end
    end)
    UIS.InputChanged:Connect(function(input)
        if input == dragInput and dragging then
            update(input)
        end
    end)
end

-- Avatar & Welcome Button (Falso) ✨
local player = game.Players.LocalPlayer

local avatarImg = Instance.new("ImageLabel", mainFrame)
avatarImg.Size = UDim2.new(0, 55, 0, 55)
avatarImg.Position = UDim2.new(0.5, -27, 0.22, 0)
avatarImg.BackgroundTransparency = 1
avatarImg.Image = game.Players:GetUserThumbnailAsync(player.UserId, Enum.ThumbnailType.HeadShot, Enum.ThumbnailSize.Size100x100)

local avatarCorner = Instance.new("UICorner", avatarImg)
avatarCorner.CornerRadius = UDim.new(1, 0)

-- Lo creamos como botón de adorno
local welcomeButton = Instance.new("TextButton", mainFrame)
welcomeButton.Size = UDim2.new(1, 0, 0, 25)
welcomeButton.Position = UDim2.new(0, 0, 0.25, 60)
welcomeButton.BackgroundTransparency = 1
welcomeButton.Font = Enum.Font.Bodoni
welcomeButton.TextSize = 20
welcomeButton.RichText = true
welcomeButton.Text = "<i>hello, i've waited here\nfor you,\neverlong !</i>"
welcomeButton.AutoButtonColor = false -- Para que no haga sombras grises al hacer clic

-- Botón de minimizar en forma de corazón cuqui 🤍
local minimizeBtn = Instance.new("TextButton", mainFrame)
minimizeBtn.Size = UDim2.new(0, 30, 0, 30)
minimizeBtn.Position = UDim2.new(1, -35, 0, 8)
minimizeBtn.BackgroundTransparency = 1
minimizeBtn.Font = Enum.Font.Bodoni
minimizeBtn.TextSize = 20
minimizeBtn.Text = "♡"
minimizeBtn.AutoButtonColor = false

-- Función para esconder/mostrar
local function toggleMenu()
    local isOpen = mainFrame.Visible
    mainFrame.Visible = not isOpen
    toggleButton.Visible = isOpen
end

minimizeBtn.MouseButton1Click:Connect(toggleMenu)
toggleButton.MouseButton1Click:Connect(toggleMenu)

-- ESP Button (center)
local espButton = Instance.new("TextButton", mainFrame)
espButton.Size = UDim2.new(0, 100, 0, 40)
espButton.Position = UDim2.new(0.5, -50, 0.6, 0)
espButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
espButton.Text = "ESP"
espButton.BackgroundColor3 = Color3.fromRGB(250, 246, 240)
espButton.RichText = true
espButton.Font=Enum.Font.Bodoni
espButton.Text = "<i>ESP</i>"
espButton.TextSize = 24
espButton.BorderSizePixel = 0

-- Infinite Yield Button (right)
local infiniteYieldButton = Instance.new("TextButton", mainFrame)
infiniteYieldButton.Size = UDim2.new(0, 100, 0, 40)
infiniteYieldButton.Position = UDim2.new(1, -110, 0.6, 0)
infiniteYieldButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
infiniteYieldButton.Text = "infinite yield"
infiniteYieldButton.BackgroundColor3 = Color3.fromRGB(250, 246, 240)
infiniteYieldButton.RichText = true
infiniteYieldButton.Text = "<i>infinite yield</i>"
infiniteYieldButton.Font = Enum.Font.Bodoni
infiniteYieldButton.TextSize = 20
infiniteYieldButton.BorderSizePixel = 0
infiniteYieldButton.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
end)

-- Teleport Menu Button (left)
local teleportButton = Instance.new("TextButton", mainFrame)
teleportButton.Size = UDim2.new(0, 110, 0, 40) -- (Ajusta tamaño/posición según lo tengas)
teleportButton.Position = UDim2.new(0, 10, 0, 180) 
teleportButton.BackgroundColor3 = Color3.fromRGB(250, 246, 240) -- Fondo Blanco Crema
teleportButton.Font = Enum.Font.Bodoni
teleportButton.TextSize = 18 -- Más pequeño
teleportButton.RichText = true
teleportButton.Text = "<i>teleport menu</i>"
teleportButton.BorderSizePixel = 0

-- Teleport Menu Logic
teleportButton.MouseButton1Click:Connect(function()
    local tg = Instance.new("ScreenGui", game.CoreGui)
    tg.Name = "TeleportMenuGui"
    tg.ResetOnSpawn = false
    tg.IgnoreGuiInset = true

    local tf = Instance.new("Frame", tg)
    tf.Size = UDim2.new(0, 250, 0, 300)
    tf.Position = UDim2.new(0.5, -125, 0.5, -150)
    tf.BackgroundColor3 = Color3.new(250, 246, 240)
    tf.BorderSizePixel = 0

   -- Title
local title = Instance.new("TextLabel", tf)
title.Size = UDim2.new(1, 0, 0, 40)
title.BackgroundTransparency = 1
title.Font = Enum.Font.Bodoni
title.TextSize = 20
title.RichText = true
title.Text = "<i>teleport menu</i>"
title.TextColor3 = Color3.fromRGB(30, 30, 30) -- O ponle el color que prefieras
title.TextStrokeTransparency = 0.8

task.spawn(function()
    while title and title.Parent do
        -- (os.clock() % 5) / 5  --> Ciclo perfecto de 5 segundos
        local currentColor = Color3.fromHSV((os.clock() % 5) / 5, 1, 1)
        title.TextColor3 = currentColor
        task.wait(0.05)
    end
end)
    -- Scroll list
    local sc = Instance.new("ScrollingFrame", tf)
    sc.Size = UDim2.new(1, 0, 1, -40)
    sc.Position = UDim2.new(0, 0, 0, 40)
    sc.BackgroundTransparency = 1
    sc.ScrollBarThickness = 8
    sc.AutomaticCanvasSize = Enum.AutomaticSize.Y
    sc.ClipsDescendants = true

    local layout = Instance.new("UIListLayout", sc)
    layout.Padding = UDim.new(0, 5)
    layout.SortOrder = Enum.SortOrder.Name

    local btns = {}
    local function makeBtn(plr)
        if plr == LocalPlayer or btns[plr] then return end
       local b = Instance.new("TextButton", sc)
b.Size = UDim2.new(1, -10, 0, 35)
b.BackgroundColor3 = Color3.fromRGB(240, 235, 225) -- Blanco crema claro
b.Font = Enum.Font.Bodoni                          -- Fuente Bodoni
b.TextSize = 15
b.RichText = true                                  -- Activamos RichText para la cursiva
b.Text = "<i>" .. plr.Name .. "</i>"               -- Nombre en cursiva
b.TextColor3 = Color3.fromRGB(40, 40, 40)          -- Texto oscuro legible
b.BorderSizePixel = 0
        b.MouseButton1Click:Connect(function()
            if plr.Character and plr.Character:FindFirstChild("HumanoidRootPart")
            and LocalPlayer.Character and LocalPlayer.Character.PrimaryPart then
                LocalPlayer.Character:SetPrimaryPartCFrame(
                    plr.Character.HumanoidRootPart.CFrame
                )
            end
        end)
        btns[plr] = b
    end

    local function removeBtn(plr)
        if btns[plr] then
            btns[plr]:Destroy()
            btns[plr] = nil
        end
    end

    for _, plr in pairs(Players:GetPlayers()) do makeBtn(plr) end
    Players.PlayerAdded:Connect(makeBtn)
    Players.PlayerRemoving:Connect(removeBtn)

    -- Dragging for teleportFrame
    do
        local d, di, ds, sp
        local function up(inp)
            local dt = inp.Position - ds
            tf.Position = UDim2.new(sp.X.Scale, sp.X.Offset+dt.X,
                                    sp.Y.Scale, sp.Y.Offset+dt.Y)
        end
        tf.InputBegan:Connect(function(inp)
            if inp.UserInputType==Enum.UserInputType.MouseButton1
            or inp.UserInputType==Enum.UserInputType.Touch then
                d = true; ds = inp.Position; sp = tf.Position
                inp.Changed:Connect(function()
                    if inp.UserInputState==Enum.UserInputState.End then d=false end
                end)
            end
        end)
        tf.InputChanged:Connect(function(inp)
            if inp.UserInputType==Enum.UserInputType.MouseMovement
            or inp.UserInputType==Enum.UserInputType.Touch then di=inp end
        end)
        UIS.InputChanged:Connect(function(inp)
            if inp==di and d then up(inp) end
        end)
    end
end)

-- ESP Logic
local espOn = false
local function highlight(plr)
    if plr.Character and plr.Character:FindFirstChild("HumanoidRootPart")
    and not plr.Character:FindFirstChild("ESPHighlight") then
        local h = Instance.new("Highlight", plr.Character)
        h.Adornee = plr.Character
        h.FillColor = Color3.fromRGB(255, 0, 0)
        h.OutlineColor = Color3.new(1,1,1)
        h.FillTransparency = 0.5
        h.OutlineTransparency = 0
        h.Name = "ESPHighlight"
    end
end

local function runESP()
    while espOn do
        for _, plr in pairs(Players:GetPlayers()) do
            if plr~=LocalPlayer then highlight(plr) end
        end
        wait(1)
    end
end

espButton.MouseButton1Click:Connect(function()
    espOn = not espOn
    espButton.Text = espOn and "ESP: ON" or "ESP"
    if espOn then
        runESP()
    end
end)

-- 7y7d Button
local dexButton = Instance.new("TextButton", mainFrame)
dexButton.Size = UDim2.new(0, 180, 0, 40)
dexButton.Position = UDim2.new(0, 10, 1, -50) -- Ajusta la posición si es necesario
dexButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
dexButton.Text = "7y7d"
dexButton.BackgroundColor3 = Color3.fromRGB(250, 246, 240)
dexButton.RichText = true
dexButton.Text = "<i>7y7d</i>"
dexButton.Font = Enum.Font.Bodoni
dexButton.TextSize = 16
dexButton.BorderSizePixel = 0

dexButton.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/7yd7/Hub/refs/heads/Branch/GUIS/Emotes.lua"))()
end)

-- berry ave outfit stealer Button (bottom right)
local flingButton = Instance.new("TextButton", mainFrame)
flingButton.Size = UDim2.new(0, 180, 0, 40)
flingButton.Position = UDim2.new(1, -190, 1, -50)  -- bottom right corner
flingButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
flingButton.Text = "berry ave outfit stealer"
flingButton.BackgroundColor3 = Color3.fromRGB(250, 246, 240)
flingButton.RichText = true
flingButton.Text = "<i>berry ave outfit stealer</i>"
flingButton.Font = Enum.Font.Bodoni
flingButton.TextSize = 16
flingButton.BorderSizePixel = 0

flingButton.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/RoyalLorde771/stealer/refs/heads/main/berryavesteal"))()
end)

spawn(function()
    local t = 0
    while true do
local t = workspace:GetServerTimeNow()
        local currentColor = Color3.fromHSV(t % 1, 1, 1) -- 
        
        rainbowLabel.TextColor3 = currentColor
        borderStroke.Color = currentColor
        teleportButton.TextColor3 = currentColor
        espButton.TextColor3 = currentColor
        infiniteYieldButton.TextColor3 = currentColor
        dexButton.TextColor3 = currentColor
        flingButton.TextColor3 = currentColor
        welcomeButton.TextColor3 = currentColor
       minimizeBtn.TextColor3 = currentColor

        
        wait(0.10)
    end
end)
