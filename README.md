if game.PlaceId == 286090429 then
    local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))() --someone reuploaded it so I put it in place of the original back up so guy can get free credit.
    local venyx = library.new("Glurak Hub: Arsenal", 5013109572)
    
    
    
    
    
    
    
    
    
    
    
    local page2 = venyx:addPage("Main", 5012544693)
    local Farm = page2:addSection("Aimbot")
    
    
    
    
    
    local RANKUP
        Farm:addToggle("Anti-Aim", nil, function(bool)
            loadstring(game:HttpGet("https://raw.githubusercontent.com/The3Bakers4565/Spicy-Bagel/main/Other_Scripts/Arsenal/Anti_Aim.lua"))()
            RANKUP = bool
        end)
    
    
        
    
    
    
    
    
    local RANKUP
        Farm:addToggle("Shoot To Kill All The Bitches", nil, function(bool)
            loadstring(game:HttpGet("https://raw.githubusercontent.com/GameEditor-RBLX23/momentofcheese/main/cheeeeeseweee", true))()
            RANKUP = bool
        end)
    
    
    
    
    
    
    
    
    
    local RANKUP
        Farm:addToggle("Silent Aim", nil, function(bool)
            loadstring(game:HttpGet("https://raw.githubusercontent.com/GameEditor-RBLX23/GameEditor/main/Script", true))()
            RANKUP = bool
        end)
    
    
    
    
    
    
    
    
    
    local RANKUP
        Farm:addToggle("Wall Bang", nil, function(bool)
            _G.Enable = true
    local MT = getrawmetatable(game)
    local OldIndex = MT.__index
    setreadonly(MT, false)
    MT.__index = newcclosure(function(A, B)
        if B == "Clips" then
            if _G.Enable then
                return workspace.Map
            end
        end
        return OldIndex(A, B)
    end)
            RANKUP = bool
        end)
    
    
    
    
    
    
    
    
    
    
    
    
    
    local Aimbot
        Farm:addToggle("Aimbot + Fov", nil, function(bool)
            local Camera = workspace.CurrentCamera
    local Players = game:GetService("Players")
    local RunService = game:GetService("RunService")
    local UserInputService = game:GetService("UserInputService")
    local TweenService = game:GetService("TweenService")
    local LocalPlayer = Players.LocalPlayer
    local Holding = false
    local Locked = false
    local Victim
     
    _G.AimbotEnabled = true
    _G.TeamCheck = true -- If set to true then the script would only lock your aim at enemy team members.
    _G.AimPart = "Head" -- Where the aimbot script would lock at.
    _G.Sensitivity = 0 -- How many seconds it takes for the aimbot script to officially lock onto the target's aimpart.
     
    _G.CircleSides = 188 -- How many sides the FOV circle would have.
    _G.CircleColor = Color3.fromRGB(255, 255, 255) -- (RGB) Color that the FOV circle would appear as.
    _G.CircleTransparency = 0.7 -- Transparency of the circle.
    _G.CircleRadius = 250 -- The radius of the circle / FOV.
    _G.CircleFilled = false -- Determines whether or not the circle is filled.
    _G.CircleVisible = true -- Determines whether or not the circle is visible.
    _G.CircleThickness = 0 -- The thickness of the circle.
     
    local FOVCircle = Drawing.new("Circle")
    FOVCircle.Position = Vector2.new(Camera.ViewportSize.X / 2, Camera.ViewportSize.Y / 2)
    FOVCircle.Radius = _G.CircleRadius
    FOVCircle.Filled = _G.CircleFilled
    FOVCircle.Color = _G.CircleColor
    FOVCircle.Visible = _G.CircleVisible
    FOVCircle.Radius = _G.CircleRadius
    FOVCircle.Transparency = _G.CircleTransparency
    FOVCircle.NumSides = _G.CircleSides
    FOVCircle.Thickness = _G.CircleThickness
     
    local function GetClosestPlayer()
        local MaximumDistance = _G.CircleRadius
        local Target
     
        for _, v in pairs(game.Players:GetPlayers()) do
            if v.Name ~= LocalPlayer.Name then
                if _G.TeamCheck == true then 
                    if v.Team ~= LocalPlayer.Team then
                        if workspace:FindFirstChild(v.Name) ~= nil then
                            if workspace[v.Name]:FindFirstChild("HumanoidRootPart") ~= nil then
                                if workspace[v.Name]:FindFirstChild("Humanoid") ~= nil and workspace[v.Name]:FindFirstChild("Humanoid").Health ~= 0 then
                                    local ScreenPoint = Camera:WorldToScreenPoint(workspace[v.Name]:WaitForChild("HumanoidRootPart", math.huge).Position)
                                    local VectorDistance = (Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y) - Vector2.new(ScreenPoint.X, ScreenPoint.Y)).Magnitude
     
                                    if VectorDistance < MaximumDistance then
                                        Target = v
                                    end
                                end
                            end
                        end
                    end
                else
                    if workspace:FindFirstChild(v.Name) ~= nil then
                        if workspace[v.Name]:FindFirstChild("HumanoidRootPart") ~= nil then
                            if workspace[v.Name]:FindFirstChild("Humanoid") ~= nil and workspace[v.Name]:FindFirstChild("Humanoid").Health ~= 0 then
                                local ScreenPoint = Camera:WorldToScreenPoint(workspace[v.Name]:WaitForChild("HumanoidRootPart", math.huge).Position)
                                local VectorDistance = (Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y) - Vector2.new(ScreenPoint.X, ScreenPoint.Y)).Magnitude
     
                                if VectorDistance < MaximumDistance then
                                    Target = v
                                end
                            end
                        end
                    end
                end
            end
        end
     
        return Target
    end
     
    UserInputService.InputBegan:Connect(function(Input)
        if Input.UserInputType == Enum.UserInputType.MouseButton2 then
            Holding = true
        end
    end)
     
    UserInputService.InputEnded:Connect(function(Input)
        if Input.UserInputType == Enum.UserInputType.MouseButton2 then
            Holding = false
            Locked = false
        end
    end)
     
    RunService.RenderStepped:Connect(function()
        FOVCircle.Position = Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y)
        FOVCircle.Radius = _G.CircleRadius
        FOVCircle.Filled = _G.CircleFilled
        FOVCircle.Color = _G.CircleColor
        FOVCircle.Visible = _G.CircleVisible
        FOVCircle.Radius = _G.CircleRadius
        FOVCircle.Transparency = _G.CircleTransparency
        FOVCircle.NumSides = _G.CircleSides
        FOVCircle.Thickness = _G.CircleThickness
        if Holding == true and _G.AimbotEnabled == true then
            TweenService:Create(Camera, TweenInfo.new(_G.Sensitivity, Enum.EasingStyle.Sine, Enum.EasingDirection.Out), {CFrame = CFrame.new(Camera.CFrame.Position, GetClosestPlayer().Character[_G.AimPart].Position)}):Play()
            Locked = true
        end
    end)
            Aimbot = bool
        end)
    
    
    
    
    
    
    
        
    
    
    
    
    
    
    
    
    
    
    
    
        
    local RANKUP
        Farm:addToggle("Esp", nil, function(bool)
            local Holder = Instance.new("Folder", game.CoreGui)
    Holder.Name = "ESP"
     
    local Box = Instance.new("BoxHandleAdornment")
    Box.Name = "nilBox"
    Box.Size = Vector3.new(4, 7, 4)
    Box.Color3 = Color3.new(100 / 255, 100 / 255, 100 / 255)
    Box.Transparency = 0.7
    Box.ZIndex = 0
    Box.AlwaysOnTop = true
    Box.Visible = true
     
    local NameTag = Instance.new("BillboardGui")
    NameTag.Name = "nilNameTag"
    NameTag.Enabled = false
    NameTag.Size = UDim2.new(0, 200, 0, 50)
    NameTag.AlwaysOnTop = true
    NameTag.StudsOffset = Vector3.new(0, 1.8, 0)
    local Tag = Instance.new("TextLabel", NameTag)
    Tag.Name = "Tag"
    Tag.BackgroundTransparency = 1
    Tag.Position = UDim2.new(0, -50, 0, 0)
    Tag.Size = UDim2.new(0, 300, 0, 20)
    Tag.TextSize = 20
    Tag.TextColor3 = Color3.new(100 / 255, 100 / 255, 100 / 255)
    Tag.TextStrokeColor3 = Color3.new(0 / 255, 0 / 255, 0 / 255)
    Tag.TextStrokeTransparency = 0.4
    Tag.Text = "nil"
    Tag.Font = Enum.Font.SourceSansBold
    Tag.TextScaled = false
     
    local LoadCharacter = function(v)
        repeat wait() until v.Character ~= nil
        v.Character:WaitForChild("Humanoid")
        local vHolder = Holder:FindFirstChild(v.Name)
        vHolder:ClearAllChildren()
        local b = Box:Clone()
        b.Name = v.Name .. "Box"
        b.Adornee = v.Character
        b.Parent = vHolder
        local t = NameTag:Clone()
        t.Name = v.Name .. "NameTag"
        t.Enabled = true
        t.Parent = vHolder
        t.Adornee = v.Character:WaitForChild("Head", 5)
        if not t.Adornee then
            return UnloadCharacter(v)
        end
        t.Tag.Text = v.Name
        b.Color3 = Color3.new(v.TeamColor.r, v.TeamColor.g, v.TeamColor.b)
        t.Tag.TextColor3 = Color3.new(v.TeamColor.r, v.TeamColor.g, v.TeamColor.b)
        local Update
        local UpdateNameTag = function()
            if not pcall(function()
                v.Character.Humanoid.DisplayDistanceType = Enum.HumanoidDisplayDistanceType.None
                local maxh = math.floor(v.Character.Humanoid.MaxHealth)
                local h = math.floor(v.Character.Humanoid.Health)
                t.Tag.Text = v.Name .. "\n" .. ((maxh ~= 0 and tostring(math.floor((h / maxh) * 100))) or "0") .. "%  " .. tostring(h) .. "/" .. tostring(maxh)
            end) then
                Update:Disconnect()
            end
        end
        UpdateNameTag()
        Update = v.Character.Humanoid.Changed:Connect(UpdateNameTag)
    end
     
    local UnloadCharacter = function(v)
        local vHolder = Holder:FindFirstChild(v.Name)
        if vHolder and (vHolder:FindFirstChild(v.Name .. "Box") ~= nil or vHolder:FindFirstChild(v.Name .. "NameTag") ~= nil) then
            vHolder:ClearAllChildren()
        end
    end
     
    local LoadPlayer = function(v)
        local vHolder = Instance.new("Folder", Holder)
        vHolder.Name = v.Name
        v.CharacterAdded:Connect(function()
            pcall(LoadCharacter, v)
        end)
        v.CharacterRemoving:Connect(function()
            pcall(UnloadCharacter, v)
        end)
        v.Changed:Connect(function(prop)
            if prop == "TeamColor" then
                UnloadCharacter(v)
                wait()
                LoadCharacter(v)
            end
        end)
        LoadCharacter(v)
    end
     
    local UnloadPlayer = function(v)
        UnloadCharacter(v)
        local vHolder = Holder:FindFirstChild(v.Name)
        if vHolder then
            vHolder:Destroy()
        end
    end
     
    for i,v in pairs(game:GetService("Players"):GetPlayers()) do
        spawn(function() pcall(LoadPlayer, v) end)
    end
     
    game:GetService("Players").PlayerAdded:Connect(function(v)
        pcall(LoadPlayer, v)
    end)
     
    game:GetService("Players").PlayerRemoving:Connect(function(v)
        pcall(UnloadPlayer, v)
    end)
     
    game:GetService("Players").LocalPlayer.NameDisplayDistance = 0
            RANKUP = bool
        end)
    
    
    
    
    
    
    
    
    
    
    getgenv().speed = 500
    local autofarm
        Farm:addToggle("Aimbot", nil, function(bool)
            local Camera = workspace.CurrentCamera
    local Players = game:GetService("Players")
    local RunService = game:GetService("RunService")
    local UserInputService = game:GetService("UserInputService")
    local TweenService = game:GetService("TweenService")
    local LocalPlayer = Players.LocalPlayer
    local Holding = false
    local Locked = false
    local Victim
     
    _G.AimbotEnabled = true
    _G.TeamCheck = true -- If set to true then the script would only lock your aim at enemy team members.
    _G.AimPart = "Head" -- Where the aimbot script would lock at.
    _G.Sensitivity = 0 -- How many seconds it takes for the aimbot script to officially lock onto the target's aimpart.
     
    _G.CircleSides = 188 -- How many sides the FOV circle would have.
    _G.CircleColor = Color3.fromRGB(255, 255, 255) -- (RGB) Color that the FOV circle would appear as.
    _G.CircleTransparency = 0.7 -- Transparency of the circle.
    _G.CircleRadius = 400 -- The radius of the circle / FOV.
    _G.CircleFilled = false -- Determines whether or not the circle is filled.
    _G.CircleVisible = false -- Determines whether or not the circle is visible.
    _G.CircleThickness = 0 -- The thickness of the circle.
     
    local FOVCircle = Drawing.new("Circle")
    FOVCircle.Position = Vector2.new(Camera.ViewportSize.X / 2, Camera.ViewportSize.Y / 2)
    FOVCircle.Radius = _G.CircleRadius
    FOVCircle.Filled = _G.CircleFilled
    FOVCircle.Color = _G.CircleColor
    FOVCircle.Visible = _G.CircleVisible
    FOVCircle.Radius = _G.CircleRadius
    FOVCircle.Transparency = _G.CircleTransparency
    FOVCircle.NumSides = _G.CircleSides
    FOVCircle.Thickness = _G.CircleThickness
     
    local function GetClosestPlayer()
        local MaximumDistance = _G.CircleRadius
        local Target
     
        for _, v in pairs(game.Players:GetPlayers()) do
            if v.Name ~= LocalPlayer.Name then
                if _G.TeamCheck == true then 
                    if v.Team ~= LocalPlayer.Team then
                        if workspace:FindFirstChild(v.Name) ~= nil then
                            if workspace[v.Name]:FindFirstChild("HumanoidRootPart") ~= nil then
                                if workspace[v.Name]:FindFirstChild("Humanoid") ~= nil and workspace[v.Name]:FindFirstChild("Humanoid").Health ~= 0 then
                                    local ScreenPoint = Camera:WorldToScreenPoint(workspace[v.Name]:WaitForChild("HumanoidRootPart", math.huge).Position)
                                    local VectorDistance = (Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y) - Vector2.new(ScreenPoint.X, ScreenPoint.Y)).Magnitude
     
                                    if VectorDistance < MaximumDistance then
                                        Target = v
                                    end
                                end
                            end
                        end
                    end
                else
                    if workspace:FindFirstChild(v.Name) ~= nil then
                        if workspace[v.Name]:FindFirstChild("HumanoidRootPart") ~= nil then
                            if workspace[v.Name]:FindFirstChild("Humanoid") ~= nil and workspace[v.Name]:FindFirstChild("Humanoid").Health ~= 0 then
                                local ScreenPoint = Camera:WorldToScreenPoint(workspace[v.Name]:WaitForChild("HumanoidRootPart", math.huge).Position)
                                local VectorDistance = (Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y) - Vector2.new(ScreenPoint.X, ScreenPoint.Y)).Magnitude
     
                                if VectorDistance < MaximumDistance then
                                    Target = v
                                end
                            end
                        end
                    end
                end
            end
        end
     
        return Target
    end
     
    UserInputService.InputBegan:Connect(function(Input)
        if Input.UserInputType == Enum.UserInputType.MouseButton2 then
            Holding = true
        end
    end)
     
    UserInputService.InputEnded:Connect(function(Input)
        if Input.UserInputType == Enum.UserInputType.MouseButton2 then
            Holding = false
            Locked = false
        end
    end)
     
    RunService.RenderStepped:Connect(function()
        FOVCircle.Position = Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y)
        FOVCircle.Radius = _G.CircleRadius
        FOVCircle.Filled = _G.CircleFilled
        FOVCircle.Color = _G.CircleColor
        FOVCircle.Visible = _G.CircleVisible
        FOVCircle.Radius = _G.CircleRadius
        FOVCircle.Transparency = _G.CircleTransparency
        FOVCircle.NumSides = _G.CircleSides
        FOVCircle.Thickness = _G.CircleThickness
        if Holding == true and _G.AimbotEnabled == true then
            TweenService:Create(Camera, TweenInfo.new(_G.Sensitivity, Enum.EasingStyle.Sine, Enum.EasingDirection.Out), {CFrame = CFrame.new(Camera.CFrame.Position, GetClosestPlayer().Character[_G.AimPart].Position)}):Play()
            Locked = true
        end
    end)
            autofarm = bool
        end)
    
    
    
    
        
        local Farm = page2:addSection("Visual")
        local RANKUP
        
        
        
        
        

    
    
    
    
    
    
    
    
    
    
    
    
        local Fov
        Farm:addToggle("Fov", nil, function(bool)
            _G.CircleSides = 64 -- How many sides the FOV circle would have.
    _G.CircleColor = Color3.fromRGB(255, 255, 255) -- (RGB) Color that the FOV circle would appear as.
    _G.CircleTransparency = 0.7 -- Transparency of the circle.
    _G.CircleRadius = 80 -- The radius of the circle / FOV.
    _G.CircleFilled = false -- Determines whether or not the circle is filled.
    _G.CircleVisible = true -- Determines whether or not the circle is visible.
    _G.CircleThickness = 0 -- The thickness of the circle.
     
    local FOVCircle = Drawing.new("Circle")
    FOVCircle.Position = Vector2.new(Camera.ViewportSize.X / 2, Camera.ViewportSize.Y / 2)
    FOVCircle.Radius = _G.CircleRadius
    FOVCircle.Filled = _G.CircleFilled
    FOVCircle.Color = _G.CircleColor
    FOVCircle.Visible = _G.CircleVisible
    FOVCircle.Radius = _G.CircleRadius
    FOVCircle.Transparency = _G.CircleTransparency
    FOVCircle.NumSides = _G.CircleSides
    FOVCircle.Thickness = _G.CircleThickness
     
    local function GetClosestPlayer()
        local MaximumDistance = _G.CircleRadius
        local Target
     
        for _, v in pairs(game.Players:GetPlayers()) do
            if v.Name ~= LocalPlayer.Name then
                if _G.TeamCheck == true then 
                    if v.Team ~= LocalPlayer.Team then
                        if workspace:FindFirstChild(v.Name) ~= nil then
                            if workspace[v.Name]:FindFirstChild("HumanoidRootPart") ~= nil then
                                if workspace[v.Name]:FindFirstChild("Humanoid") ~= nil and workspace[v.Name]:FindFirstChild("Humanoid").Health ~= 0 then
                                    local ScreenPoint = Camera:WorldToScreenPoint(workspace[v.Name]:WaitForChild("HumanoidRootPart", math.huge).Position)
                                    local VectorDistance = (Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y) - Vector2.new(ScreenPoint.X, ScreenPoint.Y)).Magnitude
     
                                    if VectorDistance < MaximumDistance then
                                        Target = v
                                    end
                                end
                            end
                        end
                    end
                else
                    if workspace:FindFirstChild(v.Name) ~= nil then
                        if workspace[v.Name]:FindFirstChild("HumanoidRootPart") ~= nil then
                            if workspace[v.Name]:FindFirstChild("Humanoid") ~= nil and workspace[v.Name]:FindFirstChild("Humanoid").Health ~= 0 then
                                local ScreenPoint = Camera:WorldToScreenPoint(workspace[v.Name]:WaitForChild("HumanoidRootPart", math.huge).Position)
                                local VectorDistance = (Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y) - Vector2.new(ScreenPoint.X, ScreenPoint.Y)).Magnitude
     
                                if VectorDistance < MaximumDistance then
                                    Target = v
                                end
                            end
                        end
                    end
                end
            end
        end
     
        return Target
    end
     
    UserInputService.InputBegan:Connect(function(Input)
        if Input.UserInputType == Enum.UserInputType.MouseButton2 then
            Holding = true
        end
    end)
     
    UserInputService.InputEnded:Connect(function(Input)
        if Input.UserInputType == Enum.UserInputType.MouseButton2 then
            Holding = false
            Locked = false
        end
    end)
     
    RunService.RenderStepped:Connect(function()
        FOVCircle.Position = Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y)
        FOVCircle.Radius = _G.CircleRadius
        FOVCircle.Filled = _G.CircleFilled
        FOVCircle.Color = _G.CircleColor
        FOVCircle.Visible = _G.CircleVisible
        FOVCircle.Radius = _G.CircleRadius
        FOVCircle.Transparency = _G.CircleTransparency
        FOVCircle.NumSides = _G.CircleSides
        FOVCircle.Thickness = _G.CircleThickness
        if Holding == true and _G.AimbotEnabled == true then
            TweenService:Create(Camera, TweenInfo.new(_G.Sensitivity, Enum.EasingStyle.Sine, Enum.EasingDirection.Out), {CFrame = CFrame.new(Camera.CFrame.Position, GetClosestPlayer().Character[_G.AimPart].Position)}):Play()
            Locked = true
        end
    end)
            Fov = bool
        end)
    
        
        local RANKUP
        Farm:addToggle("One hit all", nil, function(bool)
             
    local met = getrawmetatable(game)
    setreadonly(met,false)
    local old = met.__namecall
    met.__namecall = function(t,...)
    local args = {...}
    if(getnamecallmethod()=="FireServer") then
    if(tostring(t) == "HitPart") then
      for i = 0,25 do old(t,...)end
    end
     
    end
    return old(t,...)
    end
            RANKUP = bool
        end)
        
        
        local d = page2:addSection("click first on fov + aimbot and then on fov")
    
    
    
            local Farm = page2:addSection("Kill Aura")
            local RANKUP
        Farm:addToggle("Kill Aura", nil, function(bool)
            _G.Range = 25
    
            loadstring(game:HttpGet("https://raw.githubusercontent.com/JRL-lav/Scripts/main/Arsenal"))() 
            RANKUP = bool
        end)
    
    
    
    
        
    
    
        local page3 = venyx:addPage("Local Player", 5012544693)
        local Farm = page3:addSection("Local Player")
    
        local InfJump
        Farm:addToggle("Infinite Jump", nil, function(bool)
            game:GetService("UserInputService").JumpRequest:connect(function()
                game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")      
            end)
            InfJump = bool
        end)
    
        local RANKUP
        Farm:addToggle("Fly (E)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/7rXZ9VNc", true))()
            RANKUP = bool
        end)
    



    
       



    
        local RANKUP
        Farm:addToggle("Noclip (R)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/2pwTjwS4", true))()
            RANKUP = bool
        end)
    
    
        local RANKUP
        Farm:addToggle("God Mode", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/MSZAznxp", true))()
            RANKUP = bool
        end)
    
    
        local RANKUP
        Farm:addToggle("Anti-Afk", nil, function(bool)
            wait(0.5)local ba=Instance.new("ScreenGui")
    local ca=Instance.new("TextLabel")local da=Instance.new("Frame")
    local _b=Instance.new("TextLabel")local ab=Instance.new("TextLabel")ba.Parent=game.CoreGui
    ba.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;ca.Parent=ba;ca.Active=true
    ca.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ca.Draggable=true
    ca.Position=UDim2.new(0.698610067,0,0.098096624,0)ca.Size=UDim2.new(0,304,0,52)
    ca.Font=Enum.Font.SourceSansSemibold;ca.Text="Anti Afk Kick Script"ca.TextColor3=Color3.new(0,1,1)
    ca.TextSize=22;da.Parent=ca
    da.BackgroundColor3=Color3.new(0.196078,0.196078,0.196078)da.Position=UDim2.new(0,0,1.0192306,0)
    da.Size=UDim2.new(0,304,0,107)_b.Parent=da
    _b.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)_b.Position=UDim2.new(0,0,0.800455689,0)
    _b.Size=UDim2.new(0,304,0,21)_b.Font=Enum.Font.Arial;_b.Text="Made by: RealLeon#0005"
    _b.TextColor3=Color3.new(1,1,1)_b.TextSize=20;ab.Parent=da
    ab.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ab.Position=UDim2.new(0,0,0.158377379,0)
    ab.Size=UDim2.new(0,304,0,44)ab.Font=Enum.Font.ArialBold;ab.Text="Status: Script Started"
    ab.TextColor3=Color3.new(1,1,1)ab.TextSize=20;local bb=game:service'VirtualUser'
    game:service'Players'.LocalPlayer.Idled:connect(function()
    bb:CaptureController()bb:ClickButton2(Vector2.new())
    ab.Text="You went idle and ROBLOX tried to kick you but we reflected it!"wait(2)ab.Text="Script Re-Enabled"end)
            RANKUP = bool
        end)
    
    

    
    
    
        
    
        
    
    
    
    
    
    
    
    
    
        
    
        local page4 = venyx:addPage("Aim Help", 5012544693)
        local Farm = page4:addSection("Aim Help")
        local Farm = page4:addSection("Click on Aimbot and turn it on")
        local Farm = page4:addSection("Than click on play")
        local Farm = page4:addSection("Press in Game Right Click")
        local Farm = page4:addSection("Is it Works?")
        local Farm = page4:addSection("If it lags has join them my discord server-")
        local Farm = page4:addSection("and write to me then tell them what the problem is")
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    local page5 = venyx:addPage("Credits", 5012544693)
    local Discord = page5:addSection("Discord")
    
    
    Discord:addButton("Copy Discord Link", function()
        setclipboard("https://discord.gg/F6dSgpUPBG")
    end)
    local Discord = page5:addSection("Credits")
    local d = page5:addSection("Made by: Leon💙#0005")
    local d = page5:addSection("Scripter: Leon💙#0005")
    local d = page5:addSection("Script Developers: /Leon💙#0005/Yomama#0001/NezyGhoul#8130/")
    
    
    -- themes
    local themes = {
    Background = Color3.fromRGB(24, 24, 24),
    Glow = Color3.fromRGB(0, 0, 0),
    Accent = Color3.fromRGB(10, 10, 10),
    LightContrast = Color3.fromRGB(20, 20, 20),
    DarkContrast = Color3.fromRGB(14, 14, 14),
    TextColor = Color3.fromRGB(255, 255, 255)
    }
    
        
    -- Theme page
    local settings = venyx:addPage("Settings", 5012544693)
    local colors = settings:addSection("Colors")
    local setting = settings:addSection("Settings")
    
    setting:addKeybind("Show/Hide Settings", Enum.KeyCode.P, function()
    print("Activated Keybind")
    venyx:toggle()
    end, function()
    print("Changed Keybind")
    end)
    
    for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
    colors:addColorPicker(theme, color, function(color3)
    venyx:setTheme(theme, color3)
    end)
    end
    
    -- load
    venyx:SelectPage(venyx.pages[1], true) -- no default for more freedom
    end













































































    



    if game.PlaceId == 2788229376 then
        local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))() --someone reuploaded it so I put it in place of the original back up so guy can get free credit.
        local venyx = library.new("Glurak Hub: Da Hood", 5013109572)

        






        local page1 = venyx:addPage("Local Player", 5012544693)
        local Farm = page1:addSection("ESP")





        local RANKUP
        Farm:addToggle("Esp", nil, function(bool)
            local MainParent = game.workspace.Terrain or nil
local LineFrame = Instance.new("ScreenGui",MainParent)
LineFrame.Name = "Lines"
LineFrame.Enabled = false
ToggleKey = Enum.KeyCode.F1
local Spotted = {};
local CharacterMotors = {}
CharacterMotors.GetMotors = function(char)
    local Motors = {}
        for i,v in pairs(char:GetDescendants()) do
            if v:IsA("Motor6D") then
                if v.Part0 and v.Part1 then--and v.Part0.Name ~= "HumanoidRootPart" and v.Part1.Name ~= "HumanoidRootPart" then
                    table.insert(Motors,{v.Part0,v.Part1})
                end
            end
        end
    table.insert(Motors,{char:FindFirstChild("Head") or char.PrimaryPart,"Camera"})
    CharacterMotors[char] = Motors
    return CharacterMotors[char]
end
        
lerp = function(a, b, t)
    return a + (b - a) * t
end
 
local ESP = {Characters = {}}
ESP.Visible = true
ESP.Init = function(char,plr)
    --if (game:GetService("Players").LocalPlayer.Team == nil or plr.Team ~= game:GetService("Players").LocalPlayer.Team) then
        char.DescendantAdded:Connect(function()
            CharacterMotors.GetMotors(char)
        end)
        
        local BillboardUi = Instance.new("BillboardGui")
        BillboardUi.AlwaysOnTop = true
        BillboardUi.Size = UDim2.new(3,60,1,30)
        BillboardUi.StudsOffsetWorldSpace = Vector3.new(0,-4.5,0)
        BillboardUi.Adornee = char:WaitForChild("HumanoidRootPart")
        
        local PlayerName = Instance.new("TextLabel",BillboardUi)
        PlayerName.BackgroundTransparency = 1
        PlayerName.TextColor3 = (game:GetService("Players"):GetPlayerFromCharacter(char)).TeamColor.Color
        PlayerName.Size = UDim2.new(1,0,.3,0)
        PlayerName.ZIndex = 2
        PlayerName.Text = char.Name
        PlayerName.TextScaled = true
        PlayerName.TextStrokeTransparency = .25
        PlayerName.Font = Enum.Font.GothamBold
        PlayerName.TextStrokeColor3 = Color3.fromRGB(33, 33, 33)
        
        local Distance = PlayerName:Clone()
        Distance.Parent = BillboardUi
        Distance.Font = Enum.Font.Gotham
        Distance.TextColor3 = Color3.new(1,1,1)
        Distance.Position = UDim2.new(0,0,.3,0)
        
        local Health = PlayerName:Clone()
        Health.Parent = BillboardUi
        Health.Font = Enum.Font.Gotham
        Health.Position = UDim2.new(0,0,.6,0)
        
        ESP.Characters[char] = {PlayerName,Distance,Health,BillboardUi}
    --end
end
ESP.Render = function()
    
    for i,v in pairs(ESP.Characters) do
        pcall(function()
            local shrink = ((((game.Workspace.CurrentCamera.CFrame.p) - i.HumanoidRootPart.Position).Magnitude)/1500)+1
            v[2].Text = math.floor(((game.Workspace.CurrentCamera.CFrame.p) - i.HumanoidRootPart.Position).Magnitude+.5)
            v[3].Text = math.floor(i.Humanoid.Health).."/"..i.Humanoid.MaxHealth.." - "..math.floor(((i.Humanoid.Health/i.Humanoid.MaxHealth)*100)+.5).."%"
            v[3].TextColor3 = Color3.fromHSV((i.Humanoid.Health/i.Humanoid.MaxHealth) * (80/255),1,1)
            if not Spotted[i] then
                --v[1].TextTransparency = lerp(v[1].TextTransparency,.6,0.05)
            else
                --v[1].TextTransparency = lerp(v[1].TextTransparency,0,0.1)
            end
            v[1].TextColor3 = (game:GetService("Players"):GetPlayerFromCharacter(i)).TeamColor.Color
            --v[1].TextStrokeTransparency = 1-((1-v[1].TextTransparency)/2)
            --v[2].TextTransparency = v[1].TextTransparency
            --v[2].TextStrokeTransparency = v[1].TextStrokeTransparency
            --v[3].TextTransparency = v[1].TextTransparency
            --v[3].TextStrokeTransparency = v[1].TextStrokeTransparency
            v[4].Size = UDim2.new(3,60/shrink,1,30/shrink)
            v[1].Visible = ESP.Visible
            v[2].Visible = ESP.Visible
            v[3].Visible = ESP.Visible
            v[4].Parent = MainParent
            
        end)
    end
    
end
 
local Perspective = {}
Perspective.CalculatePoint = function(position,cam)
    local vector, onScreen = cam:WorldToScreenPoint(position)
    return Vector2.new(vector.X, vector.Y),vector.Z,onScreen
end
 
local Draw = {UsedLines = {}}
Draw.Line = function(a,b,line,width)
    if a and b then 
        local lerp = a:Lerp(b,.5)
        local Magnitude = (a-b).Magnitude
        line.AnchorPoint = Vector2.new(0.5,.5)
        line.Position = UDim2.new(lerp.X/game.Workspace.CurrentCamera.ViewportSize.X,0,(lerp.Y/(game.Workspace.CurrentCamera.ViewportSize.Y-36)),36/2)
        line.Size = UDim2.new(Magnitude/line.Parent.AbsoluteSize.X,0,0,width)
        line.Rotation = math.deg(math.atan2(a.y - b.y, a.x - b.x))
    else
        line:Destroy()
    end
end
 
 
Draw.Character = function(player,lines,cam)
    local Motors = CharacterMotors[player]
    if not Motors then
        Motors = CharacterMotors.GetMotors(player)
    end
 
    for i,v in pairs(Motors) do
        if v[1] and v[2] then
            local FoundLine = nil
            for i,v in pairs(lines:GetChildren()) do
                if Draw.UsedLines[v] == nil then
                    Draw.UsedLines[v] = true
                    FoundLine = v
                    break
                end
            end
            local a2d,az,screen = Perspective.CalculatePoint(v[1].Position,cam)
            local b2d,bz,screen2
            local v2pos = v[2].Position
            Spotted[player] = false
            if v[2] == "Camera" then
                local ray = Ray.new(v[1].Position, (cam.CFrame.p - v[1].Position).unit * (cam.CFrame.p - v[1].Position).Magnitude)
                local part, position = workspace:FindPartOnRayWithIgnoreList(ray, {game:GetService("Players").LocalPlayer.Character,player}, false, true)
                if part then
                    screen = false
                    screen2 = false
                else
                    Spotted[player] = true
                    b2d,bz,screen2 = Vector2.new(cam.ViewportSize.x/2, cam.ViewportSize.y),0,true   
                    screen = true
                end
                v2pos = v[1].Position
            else
                b2d,bz,screen2 = Perspective.CalculatePoint(v[2].Position,cam)  
            end
            if screen and screen2 and (v[1].Position-v2pos).Magnitude <= 5 then
                if not FoundLine then
                    FoundLine = Instance.new("Frame")
                    FoundLine.BackgroundColor3 = Color3.new(1,1,1)
                    FoundLine.BackgroundTransparency = .25
                    FoundLine.BorderSizePixel = 0
                    FoundLine.Parent = lines    
                    Draw.UsedLines[FoundLine] = true
                end
                if screen then
                    Draw.Line(a2d,b2d,FoundLine,1)
                else
                    Draw.Line(b2d,a2d,FoundLine,1)
                end
            elseif FoundLine then
                FoundLine:Destroy()
            end
        end
    end
end
 
Draw.ResetLines = function(lines)
    for i,v in pairs(lines:GetChildren()) do
        if Draw.UsedLines[v] == nil then
            v:Destroy()
        end
    end
    Draw.UsedLines = {}
end
 
local AddPlayer = function(plr)
    coroutine.resume(coroutine.create(function()
        if plr ~= game:GetService("Players").LocalPlayer  then
            if plr.Character then
                ESP.Init(plr.Character,plr)
            end
            plr.CharacterAdded:Connect(function(cha)
                ESP.Init(cha,plr)
            end)
        end
    end))
end
 
for i,v in pairs(game:GetService("Players"):GetChildren()) do
    AddPlayer(v)
end
game:GetService("Players").PlayerAdded:Connect(function(v)
    AddPlayer(v)
end)
game:GetService("UserInputService").InputBegan:connect(function(inputObject)
    if inputObject.KeyCode == ToggleKey then
        ESP.Visible = not ESP.Visible
    end
end)
game:GetService("RunService").RenderStepped:Connect(function()
    ESP.Render()
    for i,v in pairs(game:GetService("Players"):GetChildren()) do
        if v.Character and v ~= game:GetService("Players").LocalPlayer and (game:GetService("Players").LocalPlayer.Team == nil or v.Team ~= game:GetService("Players").LocalPlayer.Team) then
            if v.Character.PrimaryPart and (v.Character.PrimaryPart.Position - game.Workspace.CurrentCamera.CFrame.Position).Magnitude <= 200 then
                Draw.Character(v.Character,LineFrame,game.Workspace.CurrentCamera)
            end
        end
    end
    Draw.ResetLines(LineFrame)
end)

            RANKUP = bool
        end)
    
    





        local Farm = page1:addSection("Infinite Jump")
        local RANKUP
        Farm:addToggle("Inf Jump", nil, function(bool)
            game:GetService("UserInputService").JumpRequest:connect(function()
                game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")      
            end)
            RANKUP = bool
        end)
    




        local Farm = page1:addSection("Fly with (E)")
        local RANKUP
        Farm:addToggle("Fly (E)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/7rXZ9VNc", true))()
            RANKUP = bool
        end)
    

        local Farm = page1:addSection("Noclip with (R)")
        local RANKUP
        Farm:addToggle("Noclip (R)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/2pwTjwS4", true))()
            RANKUP = bool
        end)


        local Farm = page1:addSection("Alt Delet")
        local RANKUP
        Farm:addToggle("Alt Delet", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/DThr62Cn", true))()	
            RANKUP = bool
        end)


        local Farm = page1:addSection("Ctrl Teleport")
        local RANKUP
        Farm:addToggle("Ctrl Teleport", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/gp9y2Wht", true))()
            RANKUP = bool
        end)





        local Farm = page1:addSection("God Mode")
        local RANKUP
        Farm:addToggle("God Mode", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/MSZAznxp", true))()
            RANKUP = bool
        end)



        local Farm = page1:addSection("Anti-Afk")
        local RANKUP
        Farm:addToggle("Anti-Afk", nil, function(bool)
            wait(0.5)local ba=Instance.new("ScreenGui")
    local ca=Instance.new("TextLabel")local da=Instance.new("Frame")
    local _b=Instance.new("TextLabel")local ab=Instance.new("TextLabel")ba.Parent=game.CoreGui
    ba.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;ca.Parent=ba;ca.Active=true
    ca.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ca.Draggable=true
    ca.Position=UDim2.new(0.698610067,0,0.098096624,0)ca.Size=UDim2.new(0,304,0,52)
    ca.Font=Enum.Font.SourceSansSemibold;ca.Text="Anti Afk Kick Script"ca.TextColor3=Color3.new(0,1,1)
    ca.TextSize=22;da.Parent=ca
    da.BackgroundColor3=Color3.new(0.196078,0.196078,0.196078)da.Position=UDim2.new(0,0,1.0192306,0)
    da.Size=UDim2.new(0,304,0,107)_b.Parent=da
    _b.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)_b.Position=UDim2.new(0,0,0.800455689,0)
    _b.Size=UDim2.new(0,304,0,21)_b.Font=Enum.Font.Arial;_b.Text="Made by: RealLeon#0005"
    _b.TextColor3=Color3.new(1,1,1)_b.TextSize=20;ab.Parent=da
    ab.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ab.Position=UDim2.new(0,0,0.158377379,0)
    ab.Size=UDim2.new(0,304,0,44)ab.Font=Enum.Font.ArialBold;ab.Text="Status: Script Started"
    ab.TextColor3=Color3.new(1,1,1)ab.TextSize=20;local bb=game:service'VirtualUser'
    game:service'Players'.LocalPlayer.Idled:connect(function()
    bb:CaptureController()bb:ClickButton2(Vector2.new())
    ab.Text="You went idle and ROBLOX tried to kick you but we reflected it!"wait(2)ab.Text="Script Re-Enabled"end)
            RANKUP = bool
        end)




        local page2 = venyx:addPage("AutoFarm", 5012544693)
        local Farm = page2:addSection("AutoFarm Money")




        
    
    
    
    





        local RANKUP
        Farm:addToggle("AutoFarm Money", nil, function(bool)
            loadstring(game:HttpGet("https://raw.githubusercontent.com/xaxaxaxaxaxaxaxaxa/Bypasses/main/Da-Hood", true))()

if not getgenv().Settings then 
    getgenv().Settings = {
        Enabled = true, -- Dont mess with this, just rejoin the game to turn the autofarm off
        TeleportSpeed = 5, -- The Lower the Faster, the Higher the Slower
    }
end

local Players, RService, TweenService = game:GetService"Players", game:GetService"RunService", game:GetService"TweenService";
local Client, CF, INew, Vec3 = Players.LocalPlayer, CFrame.new, Instance.new, Vector3.new;

local Path = workspace:WaitForChild"Ignored".Drop

function TweenTo(Part, Speed)
    local ClientPart = Client.Character:FindFirstChild"HumanoidRootPart";
    local TweenInformation = TweenService:Create(ClientPart, TweenInfo.new(
        Speed, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {CFrame = Part}
    )
    
    if ClientPart and Part then 
        TweenInformation:Play()
    end
end

function FarmMoney()
    local SitDetection = Client.Character:WaitForChild"Humanoid".Sit
    
    while RService.RenderStepped:Wait() and getgenv().Settings.Enabled == true do 
        if SitDetection == true then 
            SitDetection = false 
        end
        
        for _, v in next, Path:GetChildren() do 
            if v and v:IsA"Part" and v.Name == "MoneyDrop" then 
                local FoundMoney = v
                local ClickDetector = FoundMoney:FindFirstChild"ClickDetector";
                local ClientPart = Client.Character:WaitForChild"HumanoidRootPart";
                
                if ClickDetector and ClientPart then 
                    TweenTo(CF(FoundMoney.Position), getgenv().Settings.TeleportSpeed)
                    
                    repeat RService.RenderStepped:Wait()
                    until ((ClientPart.Position - FoundMoney.Position).Magnitude <= ClickDetector.MaxActivationDistance)
                    
                    fireclickdetector(ClickDetector)
                end
            end
        end
    end
end
FarmMoney()

do 
    for _, v in next, workspace:GetDescendants() do 
        if v and v:IsA"Seat" then 
            v:Destroy()
        end
    end
end

Client.CharacterAdded:Connect(function()
    Client.Character:WaitForChild"Humanoid"
    
    FarmMoney()
end)

workspace.DescendantAdded:Connect(function(Descendant)
    if Descendant and Descendant:IsA"Seat" then 
        Descendant:Destroy()
    end
end)

Path.ChildAdded:Connect(function()
    FarmMoney()
end)
            RANKUP = bool
        end)

        
        
















        local Farm = page2:addSection("Auto Rob")
        local RANKUP
    Farm:addToggle("Auto Rob", nil, function(bool)
        
repeat
    wait()
until game:IsLoaded()
local gm = getrawmetatable(game)
setreadonly(gm, false)
local namecall = gm.__namecall
gm.__namecall =
    newcclosure(
    function(self, ...)
        local args = {...}
        if not checkcaller() and getnamecallmethod() == "FireServer" and tostring(self) == "MainEvent" then
            if tostring(getcallingscript()) ~= "Framework" then
                return
            end
        end
        if not checkcaller() and getnamecallmethod() == "Kick" then
            return
        end
        return namecall(self, unpack(args))
    end
)

local LocalPlayer = game:GetService("Players").LocalPlayer

function gettarget()
    local Character = LocalPlayer.Character or LocalPlayer.CharacterAdded:wait()
    local HumanoidRootPart = Character:WaitForChild("HumanoidRootPart")
    local maxdistance = math.huge
    local target
    for i, v in pairs(game:GetService("Workspace").Cashiers:GetChildren()) do
        if v:FindFirstChild("Head") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
            local distance = (HumanoidRootPart.Position - v.Head.Position).magnitude
            if distance < maxdistance then
                target = v
                maxdistance = distance
            end
        end
    end
    return target
end

for i, v in pairs(workspace:GetDescendants()) do
    if v:IsA("Seat") then
        v:Destroy()
    end
end

print("Amnesia's Da Hood Farm")

shared.MoneyFarm = true -- Just execute shared.MoneyFarm = false to stop farming

while shared.MoneyFarm do
    wait()
    local Target = gettarget()
    repeat
        wait()
        pcall(
            function()
                local Character = LocalPlayer.Character or LocalPlayer.CharacterAdded:wait()
                local HumanoidRootPart = Character:WaitForChild("HumanoidRootPart")
                local Combat = LocalPlayer.Backpack:FindFirstChild("Combat") or Character:FindFirstChild("Combat")
                if not Combat then
                    Character:FindFirstChild("Humanoid").Health = 0
                    return
                end
                HumanoidRootPart.CFrame = Target.Head.CFrame * CFrame.new(0, -2.5, 3)
                Combat.Parent = Character
                Combat:Activate()
            end
        )
    until not Target or Target.Humanoid.Health < 0
    for i, v in pairs(game:GetService("Workspace").Ignored.Drop:GetDescendants()) do
        if v:IsA("ClickDetector") and v.Parent and v.Parent.Name:find("Money") then
            local Character = LocalPlayer.Character or LocalPlayer.CharacterAdded:wait()
            local HumanoidRootPart = Character:WaitForChild("HumanoidRootPart")
            if (v.Parent.Position - HumanoidRootPart.Position).magnitude <= 18 then
                repeat
                    wait()
                    fireclickdetector(v)
                until not v or not v.Parent.Parent
            end
        end
    end
    wait(1)
end
		RANKUP = bool
    end)


    local RANKUP
    Farm:addToggle("Auto Rob Off", nil, function(bool)
        
repeat
    wait()
until game:IsLoaded()
local gm = getrawmetatable(game)
setreadonly(gm, false)
local namecall = gm.__namecall
gm.__namecall =
    newcclosure(
    function(self, ...)
        local args = {...}
        if not checkcaller() and getnamecallmethod() == "FireServer" and tostring(self) == "MainEvent" then
            if tostring(getcallingscript()) ~= "Framework" then
                return
            end
        end
        if not checkcaller() and getnamecallmethod() == "Kick" then
            return
        end
        return namecall(self, unpack(args))
    end
)

local LocalPlayer = game:GetService("Players").LocalPlayer

function gettarget()
    local Character = LocalPlayer.Character or LocalPlayer.CharacterAdded:wait()
    local HumanoidRootPart = Character:WaitForChild("HumanoidRootPart")
    local maxdistance = math.huge
    local target
    for i, v in pairs(game:GetService("Workspace").Cashiers:GetChildren()) do
        if v:FindFirstChild("Head") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
            local distance = (HumanoidRootPart.Position - v.Head.Position).magnitude
            if distance < maxdistance then
                target = v
                maxdistance = distance
            end
        end
    end
    return target
end

for i, v in pairs(workspace:GetDescendants()) do
    if v:IsA("Seat") then
        v:Destroy()
    end
end

print("Da Hood Farm")

shared.MoneyFarm = false -- Just execute shared.MoneyFarm = false to stop farming

while shared.MoneyFarm do
    wait()
    local Target = gettarget()
    repeat
        wait()
        pcall(
            function()
                local Character = LocalPlayer.Character or LocalPlayer.CharacterAdded:wait()
                local HumanoidRootPart = Character:WaitForChild("HumanoidRootPart")
                local Combat = LocalPlayer.Backpack:FindFirstChild("Combat") or Character:FindFirstChild("Combat")
                if not Combat then
                    Character:FindFirstChild("Humanoid").Health = 0
                    return
                end
                HumanoidRootPart.CFrame = Target.Head.CFrame * CFrame.new(0, -2.5, 3)
                Combat.Parent = Character
                Combat:Activate()
            end
        )
    until not Target or Target.Humanoid.Health < 0
    for i, v in pairs(game:GetService("Workspace").Ignored.Drop:GetDescendants()) do
        if v:IsA("ClickDetector") and v.Parent and v.Parent.Name:find("Money") then
            local Character = LocalPlayer.Character or LocalPlayer.CharacterAdded:wait()
            local HumanoidRootPart = Character:WaitForChild("HumanoidRootPart")
            if (v.Parent.Position - HumanoidRootPart.Position).magnitude <= 18 then
                repeat
                    wait()
                    fireclickdetector(v)
                until not v or not v.Parent.Parent
            end
        end
    end
    wait(1)
end
		RANKUP = bool
    end)






        

        












        local page5 = venyx:addPage("Credits", 5012544693)
    local Discord = page5:addSection("Discord")
    
    
    Discord:addButton("Copy Discord Link", function()
        setclipboard("https://discord.gg/fvdKvh9Csm")
    end)
    local Discord = page5:addSection("Credits")
    local d = page5:addSection("Made by: RealLeon#0005")
    local d = page5:addSection("Scripter: RealLeon#0005")
    local d = page5:addSection("Script Developers: /NezyGhoul#8130/Yomama#0001/RealLeon#0005/")
    
    -- themes
    local themes = {
    Background = Color3.fromRGB(24, 24, 24),
    Glow = Color3.fromRGB(0, 0, 0),
    Accent = Color3.fromRGB(10, 10, 10),
    LightContrast = Color3.fromRGB(20, 20, 20),
    DarkContrast = Color3.fromRGB(14, 14, 14),
    TextColor = Color3.fromRGB(255, 255, 255)
    }
    
        
    -- Theme page
    local settings = venyx:addPage("Settings", 5012544693)
    local colors = settings:addSection("Colors")
    local setting = settings:addSection("Settings")
    
    setting:addKeybind("Show/Hide Settings", Enum.KeyCode.P, function()
    print("Activated Keybind")
    venyx:toggle()
    end, function()
    print("Changed Keybind")
    end)
    
    for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
    colors:addColorPicker(theme, color, function(color3)
    venyx:setTheme(theme, color3)
    end)
    end
    
    -- load
    venyx:SelectPage(venyx.pages[1], true) -- no default for more freedom
    end








































































    if game.PlaceId == 142823291 then
        local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))() --someone reuploaded it so I put it in place of the original back up so guy can get free credit.
        local venyx = library.new("Glurak Hub: Murder Mystery 2", 5013109572)




        local page5 = venyx:addPage("Main", 5012544693)
    local Discord = page5:addSection("Discord")
    
    
    Discord:addButton("Copy Discord Link", function()
        setclipboard("https://discord.gg/fvdKvh9Csm")
    end)
    local Discord = page5:addSection("Credits")
    local d = page5:addSection("Made by: RealLeon#0005")
    local d = page5:addSection("Scripter: RealLeon#0005")
    local d = page5:addSection("Script Developers: /NezyGhoul#8130/Yomama#0001/RealLeon#0005/")
    
    
    
    
        

local page2 = venyx:addPage("Local Player", 5012544693)
 

        
   

 local Farm = page2:addSection("Infinite Jump")
    local RANKUP
    Farm:addToggle("Inf Jump", nil, function(bool)
        game:GetService("UserInputService").JumpRequest:connect(function()
            game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")      
        end)
		RANKUP = bool
    end)





    local Farm = page2:addSection("Fly with (E)")
    local RANKUP
    Farm:addToggle("Fly (E)", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/7rXZ9VNc", true))()
		RANKUP = bool
    end)




    local Farm = page2:addSection("Noclip with (R)")
    local RANKUP
    Farm:addToggle("Noclip (R)", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/2pwTjwS4", true))()		
        RANKUP = bool
    end)






    local Farm = page2:addSection("Alt Delet")
    local RANKUP
    Farm:addToggle("Alt Delet", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/DThr62Cn", true))()		
        RANKUP = bool
    end)




    local Farm = page2:addSection("Ctrl Teleport")
    local RANKUP
    Farm:addToggle("Ctrl Teleport", nil, function(bool)
        --[[local Plr = game:GetService("Players").LocalPlayer
local Mouse = Plr:GetMouse()
 
Mouse.Button1Down:connect(function()
if not game:GetService("UserInputService"):IsKeyDown(Enum.KeyCode.LeftControl) then return end
if not Mouse.Target then return end
Plr.Character:MoveTo(Mouse.Hit.p)
end)
--]]
    game:GetService("StarterGui"):SetCore("SendNotification",{
        Title = "CTRL click tp",
        Text = "Hold Ctrl then press click to a place you want to teleport to.",
        Duration = 6,
            })
        local speed = 100 -- set this lower to make it slower
        local bodyvelocityenabled = true -- set this to false if you are getting kicked
         
        local Imput = game:GetService("UserInputService")
        local Plr = game.Players.LocalPlayer
        local Mouse = Plr:GetMouse()
         
        function To(position)
        local Chr = Plr.Character
        if Chr ~= nil then
        local ts = game:GetService("TweenService")
        local char = game.Players.LocalPlayer.Character
        local hm = char.HumanoidRootPart
        local dist = (hm.Position - Mouse.Hit.p).magnitude
        local tweenspeed = dist/tonumber(speed)
        local ti = TweenInfo.new(tonumber(tweenspeed), Enum.EasingStyle.Linear)
        local tp = {CFrame = CFrame.new(position)}
        ts:Create(hm, ti, tp):Play()
        if bodyvelocityenabled == true then
        local bv = Instance.new("BodyVelocity")
        bv.Parent = hm
        bv.MaxForce = Vector3.new(100000,100000,100000)
        bv.Velocity = Vector3.new(0,0,0)
        wait(tonumber(tweenspeed))
        bv:Destroy()
        end
        end
        end
         
        Imput.InputBegan:Connect(function(input)
           if input.UserInputType == Enum.UserInputType.MouseButton1 and Imput:IsKeyDown(Enum.KeyCode.LeftControl) then
               To(Mouse.Hit.p)
           end
        end)	
        RANKUP = bool
    end)



    local Farm = page2:addSection("God Mode")
    local RANKUP
    Farm:addToggle("God Mode", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/MSZAznxp", true))()
        RANKUP = bool
    end)





    local Farm = page2:addSection("Anti-Afk")
    local RANKUP
    Farm:addToggle("Anti-Afk", nil, function(bool)
        wait(0.5)local ba=Instance.new("ScreenGui")
        local ca=Instance.new("TextLabel")local da=Instance.new("Frame")
        local _b=Instance.new("TextLabel")local ab=Instance.new("TextLabel")ba.Parent=game.CoreGui
        ba.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;ca.Parent=ba;ca.Active=true
        ca.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ca.Draggable=true
        ca.Position=UDim2.new(0.698610067,0,0.098096624,0)ca.Size=UDim2.new(0,304,0,52)
        ca.Font=Enum.Font.SourceSansSemibold;ca.Text="Anti Afk Kick Script"ca.TextColor3=Color3.new(0,1,1)
        ca.TextSize=22;da.Parent=ca
        da.BackgroundColor3=Color3.new(0.196078,0.196078,0.196078)da.Position=UDim2.new(0,0,1.0192306,0)
        da.Size=UDim2.new(0,304,0,107)_b.Parent=da
        _b.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)_b.Position=UDim2.new(0,0,0.800455689,0)
        _b.Size=UDim2.new(0,304,0,21)_b.Font=Enum.Font.Arial;_b.Text="Made by: RealLeon#0005"
        _b.TextColor3=Color3.new(1,1,1)_b.TextSize=20;ab.Parent=da
        ab.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ab.Position=UDim2.new(0,0,0.158377379,0)
        ab.Size=UDim2.new(0,304,0,44)ab.Font=Enum.Font.ArialBold;ab.Text="Status: Script Started"
        ab.TextColor3=Color3.new(1,1,1)ab.TextSize=20;local bb=game:service'VirtualUser'
        game:service'Players'.LocalPlayer.Idled:connect(function()
        bb:CaptureController()bb:ClickButton2(Vector2.new())
        ab.Text="You went idle and ROBLOX tried to kick you but we reflected it!"wait(2)ab.Text="Script Re-Enabled"end)
        RANKUP = bool
    end)



local page3 = venyx:addPage("Visual", 5012544693)
local Farm = page3:addSection("Esp")
local Esp
    Farm:addToggle("Esp", nil, function(bool)
        loadstring(game:HttpGet(('https://pastebin.com/raw/ypSsQRK6'),true))()
		Esp = bool
    end)

    local d = page3:addSection("Esp is with Gun Esp")

    

local fd = page3:addSection("Unlock Xbox Item")
                    fd:addButton("Unlock", function()
        game:GetService("ReplicatedStorage").IsXbox:FireServer()

    end)

    
    
    
    
    
  
    
    
    
    
    
    
    
    
    
   
                   
                   
                   
                   
                   
    local page8 = venyx:addPage("Teleports", 5012544693)
    
    
    

       
                    
                    
    local Title = page8:addSection("Lobby")
    Title:addButton("Teleport", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-108.25495147705, 138.3260345459, 41.639129638672)
    end)

    local Test = page8:addSection("Waiting Room")
    Test:addButton("Teleport", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-108.14199829102, 140.67608642578, 83.178932189941)
    end)





    local df = page8:addSection("Map")
    df:addButton("Teleport", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(413.26495361328, 46.076118469238, 36.120166778564)
    end)



-- themes
    local themes = {
    Background = Color3.fromRGB(24, 24, 24),
    Glow = Color3.fromRGB(0, 0, 0),
    Accent = Color3.fromRGB(10, 10, 10),
    LightContrast = Color3.fromRGB(20, 20, 20),
    DarkContrast = Color3.fromRGB(14, 14, 14),
    TextColor = Color3.fromRGB(255, 255, 255)
    }
    
        
    -- Theme page
    local settings = venyx:addPage("Settings", 5012544693)
    local colors = settings:addSection("Colors")
    local setting = settings:addSection("Settings")
    
    setting:addKeybind("Show/Hide Settings", Enum.KeyCode.P, function()
    print("Activated Keybind")
    venyx:toggle()
    end, function()
    print("Changed Keybind")
    end)
    
    for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
    colors:addColorPicker(theme, color, function(color3)
    venyx:setTheme(theme, color3)
    end)
    end











-- load
    venyx:SelectPage(venyx.pages[1], true) -- no default for more freedom
    end























    
    










































    if game.PlaceId == 1240123653 then
        local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))() --someone reuploaded it so I put it in place of the original back up so guy can get free credit.
        local venyx = library.new("Glurak Hub: Zombie Attack", 5013109572)
        
        
        
        
        
        
        











        
        
        
        
        local page2 = venyx:addPage("Local Player", 5012544693)
        local Farm = page2:addSection("Local Player")

        local Farm = page2:addSection("Infinite Jump")
    local RANKUP
    Farm:addToggle("Inf Jump", nil, function(bool)
        game:GetService("UserInputService").JumpRequest:connect(function()
            game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")      
        end)
		RANKUP = bool
    end)





    local Farm = page2:addSection("Anti-Afk")
    local RANKUP
    Farm:addToggle("Anti-Afk", nil, function(bool)
        wait(0.5)local ba=Instance.new("ScreenGui")
        local ca=Instance.new("TextLabel")local da=Instance.new("Frame")
        local _b=Instance.new("TextLabel")local ab=Instance.new("TextLabel")ba.Parent=game.CoreGui
        ba.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;ca.Parent=ba;ca.Active=true
        ca.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ca.Draggable=true
        ca.Position=UDim2.new(0.698610067,0,0.098096624,0)ca.Size=UDim2.new(0,304,0,52)
        ca.Font=Enum.Font.SourceSansSemibold;ca.Text="Anti Afk Kick Script"ca.TextColor3=Color3.new(0,1,1)
        ca.TextSize=22;da.Parent=ca
        da.BackgroundColor3=Color3.new(0.196078,0.196078,0.196078)da.Position=UDim2.new(0,0,1.0192306,0)
        da.Size=UDim2.new(0,304,0,107)_b.Parent=da
        _b.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)_b.Position=UDim2.new(0,0,0.800455689,0)
        _b.Size=UDim2.new(0,304,0,21)_b.Font=Enum.Font.Arial;_b.Text="Made by: RealLeon#0005"
        _b.TextColor3=Color3.new(1,1,1)_b.TextSize=20;ab.Parent=da
        ab.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ab.Position=UDim2.new(0,0,0.158377379,0)
        ab.Size=UDim2.new(0,304,0,44)ab.Font=Enum.Font.ArialBold;ab.Text="Status: Script Started"
        ab.TextColor3=Color3.new(1,1,1)ab.TextSize=20;local bb=game:service'VirtualUser'
        game:service'Players'.LocalPlayer.Idled:connect(function()
        bb:CaptureController()bb:ClickButton2(Vector2.new())
        ab.Text="You went idle and ROBLOX tried to kick you but we reflected it!"wait(2)ab.Text="Script Re-Enabled"end)
        RANKUP = bool
    end)



    local Farm = page2:addSection("Fly with (E)")
    local RANKUP
    Farm:addToggle("Fly (E)", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/7rXZ9VNc", true))()
		RANKUP = bool
    end)




    local Farm = page2:addSection("Noclip with (R)")
    local RANKUP
    Farm:addToggle("Noclip (R)", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/2pwTjwS4", true))()		
        RANKUP = bool
    end)






    local Farm = page2:addSection("Alt Delet")
    local RANKUP
    Farm:addToggle("Alt Delet", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/DThr62Cn", true))()		
        RANKUP = bool
    end)




    local Farm = page2:addSection("Ctrl Teleport")
    local RANKUP
    Farm:addToggle("Ctrl Teleport", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/gp9y2Wht", true))()	
        RANKUP = bool
    end)



    local Farm = page2:addSection("God Mode")
    local RANKUP
    Farm:addToggle("God Mode", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/MSZAznxp", true))()
        RANKUP = bool
    end)














local page3 = venyx:addPage("AutoFarm", 5012544693)
        local Farm = page3:addSection("AutoFarm")
        local RANKUP
        Farm:addToggle("AutoFarm", nil, function(bool)
            -- Equilibrium Special Zombie_Attack Auto_Farming Enjoy Heart
local groundDistance = 8
local Player = game:GetService("Players").LocalPlayer
local function getNearest()
local nearest, dist = nil, 99999
for _,v in pairs(game.Workspace.BossFolder:GetChildren()) do
if(v:FindFirstChild("Head")~=nil)then
local m =(Player.Character.Head.Position-v.Head.Position).magnitude
if(m<dist)then
dist = m
nearest = v
end
end
end
for _,v in pairs(game.Workspace.enemies:GetChildren()) do
if(v:FindFirstChild("Head")~=nil)then
local m =(Player.Character.Head.Position-v.Head.Position).magnitude
if(m<dist)then
dist = m
nearest = v
end
end
end
return nearest
end
_G.farm2 = true
Player.Chatted:Connect(function(m)
if(m==";autofarm false")then
_G.farm2 = false
elseif(m==";autofarm true")then
_G.farm2 = true
end
end)
_G.globalTarget = nil
game:GetService("RunService").RenderStepped:Connect(function()
if(_G.farm2==true)then
local target = getNearest()
if(target~=nil)then
game:GetService("Workspace").CurrentCamera.CFrame = CFrame.new(game:GetService("Workspace").CurrentCamera.CFrame.p, target.Head.Position)
Player.Character.HumanoidRootPart.CFrame = (target.HumanoidRootPart.CFrame * CFrame.new(0, groundDistance, 9))
_G.globalTarget = target
end
end
end)
spawn(function()
while wait() do
game.Players.LocalPlayer.Character.HumanoidRootPart.Velocity = Vector3.new(0,0,0)
game.Players.LocalPlayer.Character.Torso.Velocity = Vector3.new(0,0,0)
end
end)
while wait() do
if(_G.farm2==true and _G.globalTarget~=nil and _G.globalTarget:FindFirstChild("Head") and Player.Character:FindFirstChildOfClass("Tool"))then
local target = _G.globalTarget
game.ReplicatedStorage.Gun:FireServer({["Normal"] = Vector3.new(0, 0, 0), ["Direction"] = target.Head.Position, ["Name"] = Player.Character:FindFirstChildOfClass("Tool").Name, ["Hit"] = target.Head, ["Origin"] = target.Head.Position, ["Pos"] = target.Head.Position,})
wait()
end
end
            RANKUP = bool
        end)
    
    














    local page5 = venyx:addPage("Credits", 5012544693)
    local Discord = page5:addSection("Discord")
    
    
    Discord:addButton("Copy Discord Link", function()
        setclipboard("https://discord.gg/F6dSgpUPBG")
    end)
    local Discord = page5:addSection("Credits")
    local d = page5:addSection("Made by: Leon💙#0005")
    local d = page5:addSection("Scripter: Leon💙#0005")
    local d = page5:addSection("Script Developers: /RealLeon#0005/Yomama#0001/NezyGhoul#8130/")







    -- themes
    local themes = {
        Background = Color3.fromRGB(24, 24, 24),
        Glow = Color3.fromRGB(0, 0, 0),
        Accent = Color3.fromRGB(10, 10, 10),
        LightContrast = Color3.fromRGB(20, 20, 20),
        DarkContrast = Color3.fromRGB(14, 14, 14),
        TextColor = Color3.fromRGB(255, 255, 255)
        }
        
            
        -- Theme page
        local settings = venyx:addPage("Settings", 5012544693)
        local colors = settings:addSection("Colors")
        local setting = settings:addSection("Settings")
        
        setting:addKeybind("Show/Hide Settings", Enum.KeyCode.P, function()
        print("Activated Keybind")
        venyx:toggle()
        end, function()
        print("Changed Keybind")
        end)
        
        for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
        colors:addColorPicker(theme, color, function(color3)
        venyx:setTheme(theme, color3)
        end)
        end
    
    
    
    
    
    
    
    
    
    
    
    -- load
        venyx:SelectPage(venyx.pages[1], true) -- no default for more freedom
        end


























































        if game.PlaceId == 3956818381 then
            local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))() --someone reuploaded it so I put it in place of the original back up so guy can get free credit.
            local venyx = library.new("Glurak Hub: Ninja Legends", 5013109572)













            local page2 = venyx:addPage("Local Player", 5012544693)
        local Farm = page2:addSection("Local Player")

        local Farm = page2:addSection("Infinite Jump")
    local RANKUP
    Farm:addToggle("Inf Jump", nil, function(bool)
        game:GetService("UserInputService").JumpRequest:connect(function()
            game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")      
        end)
		RANKUP = bool
    end)





    local Farm = page2:addSection("Anti-Afk")
    local RANKUP
    Farm:addToggle("Anti-Afk", nil, function(bool)
        wait(0.5)local ba=Instance.new("ScreenGui")
        local ca=Instance.new("TextLabel")local da=Instance.new("Frame")
        local _b=Instance.new("TextLabel")local ab=Instance.new("TextLabel")ba.Parent=game.CoreGui
        ba.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;ca.Parent=ba;ca.Active=true
        ca.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ca.Draggable=true
        ca.Position=UDim2.new(0.698610067,0,0.098096624,0)ca.Size=UDim2.new(0,304,0,52)
        ca.Font=Enum.Font.SourceSansSemibold;ca.Text="Anti Afk Kick Script"ca.TextColor3=Color3.new(0,1,1)
        ca.TextSize=22;da.Parent=ca
        da.BackgroundColor3=Color3.new(0.196078,0.196078,0.196078)da.Position=UDim2.new(0,0,1.0192306,0)
        da.Size=UDim2.new(0,304,0,107)_b.Parent=da
        _b.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)_b.Position=UDim2.new(0,0,0.800455689,0)
        _b.Size=UDim2.new(0,304,0,21)_b.Font=Enum.Font.Arial;_b.Text="Made by: RealLeon#0005"
        _b.TextColor3=Color3.new(1,1,1)_b.TextSize=20;ab.Parent=da
        ab.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ab.Position=UDim2.new(0,0,0.158377379,0)
        ab.Size=UDim2.new(0,304,0,44)ab.Font=Enum.Font.ArialBold;ab.Text="Status: Script Started"
        ab.TextColor3=Color3.new(1,1,1)ab.TextSize=20;local bb=game:service'VirtualUser'
        game:service'Players'.LocalPlayer.Idled:connect(function()
        bb:CaptureController()bb:ClickButton2(Vector2.new())
        ab.Text="You went idle and ROBLOX tried to kick you but we reflected it!"wait(2)ab.Text="Script Re-Enabled"end)
        RANKUP = bool
    end)



    local Farm = page2:addSection("Fly with (E)")
    local RANKUP
    Farm:addToggle("Fly (E)", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/7rXZ9VNc", true))()
		RANKUP = bool
    end)




    local Farm = page2:addSection("Noclip with (R)")
    local RANKUP
    Farm:addToggle("Noclip (R)", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/2pwTjwS4", true))()		
        RANKUP = bool
    end)






    local Farm = page2:addSection("Alt Delete")
    local RANKUP
    Farm:addToggle("Alt Delet", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/DThr62Cn", true))()		
        RANKUP = bool
    end)




    local Farm = page2:addSection("Ctrl Teleport")
    local RANKUP
    Farm:addToggle("Ctrl Teleport", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/gp9y2Wht", true))()	
        RANKUP = bool
    end)



    local Farm = page2:addSection("God Mode")
    local RANKUP
    Farm:addToggle("God Mode", nil, function(bool)
        loadstring(game:HttpGet("https://pastebin.com/raw/MSZAznxp", true))()
        RANKUP = bool
    end)



















    local page7 = venyx:addPage("AutoFarm", 5012544693)
    


local Farm = page7:addSection("AutoFarm")
local RANKUP
    Farm:addToggle("Auto Swing", nil, function(bool)
        _G.swing = true
while _G.swing do
wait()
game.Players.LocalPlayer.ninjaEvent:FireServer("swingKatana")
end
		RANKUP = bool
    end)
    
    
    
    local Farm = page7:addSection("Auto Rank")
    local RANKUP
    Farm:addToggle("Auto Rank", nil, function(bool)
        _G.sword = true
while _G.sword do
wait()
--This script was generated by Hydroxide
local oh1 = "buyRank"
local oh2 = game:GetService("ReplicatedStorage").Ranks.Ground:GetChildren()
for i = 1,#oh2 do
game:GetService("Players").LocalPlayer.ninjaEvent:FireServer(oh1, oh2[i].Name)
end
end
		RANKUP = bool
    end)






    local Farm = page7:addSection("Auto buy Skills")
    local RANKUP
    Farm:addToggle("Auto Skills", nil, function(bool)
        _G.sword = true
while _G.sword do
wait()
--This script was generated by Hydroxide
local oh1 = "buyAllSkills"
local oh2 = {"Ground", "Astral Island", "Dragon Legend Island"}
for i = 1, #oh2 do
    game:GetService("Players").LocalPlayer.ninjaEvent:FireServer(oh1, oh2[i])
end
end
		RANKUP = bool
    end)






    local Farm = page7:addSection("Auto buy belt")
    local RANKUP
    Farm:addToggle("Auto buy belt", nil, function(bool)
        _G.sword = true
while _G.sword do
wait()
--This script was generated by Hydroxide
local oh1 = "buyAllBelts"
local oh2 = {"Ground", "Astral Island", "Golden Master Island"}
for i = 1, #oh2 do
    game:GetService("Players").LocalPlayer.ninjaEvent:FireServer(oh1, oh2[i])
end
end
		RANKUP = bool
    end)











    local Farm = page7:addSection("Auto buy Swords")
    local RANKUP
    Farm:addToggle("Auto buy Swords", nil, function(bool)
        _G.sword = true
while _G.sword do
wait()
--This script was generated by Hydroxide
local oh1 = "buyAllSwords"
local oh2 = {"Ground", "Astral Island", "Dragon Legend Island"}
for i = 1, #oh2 do
    game:GetService("Players").LocalPlayer.ninjaEvent:FireServer(oh1, oh2[i])
end
end
		RANKUP = bool
    end)




    
    





local Farm = page7:addSection("Auto Sell")

local RANKUP
    Farm:addToggle("Auto Sell", nil, function(bool)
        _G.Condition = true -- true turns it on, false turns it off
        while _G.Condition == true do
        wait(1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(84.2945251, 87069.0391, 123.435143)
        wait()
      end
		RANKUP = bool
    end)




local page9 = venyx:addPage("Elements", 5012544693)


local Title = page9:addSection("Unlock Frost Element")
     Title:addButton("Unlock Frost Element", function()
        game.ReplicatedStorage.rEvents.elementMasteryEvent:FireServer("Frost")
    end)



local fd = page9:addSection("Unlock Lightning Element")
     fd:addButton("Unlock Lightning Element", function()
    game.ReplicatedStorage.rEvents.elementMasteryEvent:FireServer("Lightning")
    end)

  
  
    
local fds = page9:addSection("Unlock Inferno Element")
     fds:addButton("Unlock Inferno Element", function()
       game.ReplicatedStorage.rEvents.elementMasteryEvent:FireServer("Inferno")
    end)
    




    local Electral = page9:addSection("Unlock Electral Chaos Element")
    Electral:addButton("Unlock Electral Chaos Element", function()
        game.ReplicatedStorage.rEvents.elementMasteryEvent:FireServer("Electral Chaos")
    end)






    local Masterful = page9:addSection("Unlock Masterful Wrath Element")
    Masterful:addButton("Unlock Masterful Wrath Element", function()
        game.ReplicatedStorage.rEvents.elementMasteryEvent:FireServer("Masterful Wrath")
    end)






    local Shadow = page9:addSection("Unlock Shadow Charge Element")
    Shadow:addButton("Unlock Shadow Charge Element", function()
        game.ReplicatedStorage.rEvents.elementMasteryEvent:FireServer("Shadow Charge")
    end)











    local Shadowfire = page9:addSection("Unlock Shadowfire Element")
    Shadowfire:addButton("Unlock Shadowfire Element", function()
        game.ReplicatedStorage.rEvents.elementMasteryEvent:FireServer("Shadowfire")
    end)









    local Eternity = page9:addSection("Unlock Eternity Storm Element")
    Eternity:addButton("Unlock Eternity Storm Element", function()
        game.ReplicatedStorage.rEvents.elementMasteryEvent:FireServer("Eternity Storm")
    end)












    local page5 = venyx:addPage("Credits", 5012544693)
    local Discord = page5:addSection("Discord")
    
    
    Discord:addButton("Copy Discord Link", function()
        setclipboard("https://discord.gg/F6dSgpUPBG")
    end)
    local Discord = page5:addSection("Credits")
    local d = page5:addSection("Made by: Leon💙#0005")
    local d = page5:addSection("Scripter: Leon💙#0005")
    local d = page5:addSection("Script Developers: /Leon💙#0005/Yomama#0001/NezyGhoul#8130/")







    -- themes
    local themes = {
        Background = Color3.fromRGB(24, 24, 24),
        Glow = Color3.fromRGB(0, 0, 0),
        Accent = Color3.fromRGB(10, 10, 10),
        LightContrast = Color3.fromRGB(20, 20, 20),
        DarkContrast = Color3.fromRGB(14, 14, 14),
        TextColor = Color3.fromRGB(255, 255, 255)
        }
        
            
        -- Theme page
        local settings = venyx:addPage("Settings", 5012544693)
        local colors = settings:addSection("Colors")
        local setting = settings:addSection("Settings")
        
        setting:addKeybind("Show/Hide Settings", Enum.KeyCode.P, function()
        print("Activated Keybind")
        venyx:toggle()
        end, function()
        print("Changed Keybind")
        end)
        
        for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
        colors:addColorPicker(theme, color, function(color3)
        venyx:setTheme(theme, color3)
        end)
        end
    
    
    
    
    
    
    
    
    
    
    
    -- load
        venyx:SelectPage(venyx.pages[1], true) -- no default for more freedom
        end












































































































        if game.PlaceId == 1224212277 then
            local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))() --someone reuploaded it so I put it in place of the original back up so guy can get free credit.
            local venyx = library.new("Glurak Hub: Mad City", 5013109572)













            local page3 = venyx:addPage("Main", 5012544693)
            
local Farm = page3:addSection("Farm Xp")
local RANKUP
    Farm:addToggle("Farm Xp", nil, function(bool)
        game:GetService("ReplicatedStorage").RemoteFunction:InvokeServer("SetTeam", "Police")
wait(.75)
game:GetService("RunService").RenderStepped:Connect(function()
for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
   if v.Name == "Handcuffs" then v.Parent = game:GetService("Players").LocalPlayer.Character
   end
end
game:GetService("ReplicatedStorage").Event:FireServer("Eject", game:GetService("Players").LocalPlayer)
end)
		RANKUP = bool
    end)






    local Farm = page3:addSection("Drive on Water")
    local RANKUP
    Farm:addToggle("Drive on Water", nil, function(bool)
        game:GetService("Workspace").ObjectSelection[game.Players.LocalPlayer.Name .. "'s Vehicle"].CarChassis.HoverMode.Value = true
		RANKUP = bool
    end)



    local Farm = page3:addSection("Walk on Water")
    local RANKUP
    Farm:addToggle("Walk on Water", nil, function(bool)
        for k,v in pairs(game:GetService("Workspace").Water:GetChildren()) do
            v.CanCollide = true
            v.Anchored = true
            v.Material = "Ice"
         end
		RANKUP = bool
    end)

            

    local Farm = page3:addSection("Infinite Nitro")
    local RANKUP
    Farm:addToggle("Infinite Nitro", nil, function(bool)
        game:GetService("RunService").RenderStepped:Connect(function()
            if workspace.ObjectSelection:FindFirstChild(game.Players.LocalPlayer.Name.."'s Vehicle") then
            pcall(function()workspace.ObjectSelection[game.Players.LocalPlayer.Name.."'s Vehicle"].CarChassis.Boost.Value = 20;end)
            end
            end)
		RANKUP = bool
    end)



    local Farm = page3:addSection("Crash Server")
    local RANKUP
    Farm:addToggle("Crash Server", nil, function(bool)
        loadstring(game:HttpGet(('https://raw.githubusercontent.com/Cesare0328/my-scripts/main/Mad%20Shitty%20instant%20crash%20server'),true))()
		RANKUP = bool
    end)




    local dfdf = page3:addSection("Rejoin Server")
    
    
    dfdf:addButton("Rejoin", function()
        game:GetService("TeleportService"):Teleport(game.PlaceId)
    end)







            



    local page4 = venyx:addPage("Weapons", 5012544693)
    local Farm = page4:addSection("Inf Ammo")
    local RANKUP
    Farm:addToggle("Inf Ammo", nil, function(bool)
        local function main(v)
            if v.Name == "RifleScript" or v.Name == "ShotgunScript" or v.Name == "PistolScript" or v.Name == "TazerScript" or v.Name == "PowerScript" then
                local a = getsenv(v)
                if debug.getupvalues(a.Reload) then
                    debug.setupvalue(a.Reload, 2, math.huge)
                end
            end
         end
         
         for _, v in pairs(game.Players.LocalPlayer.Backpack:GetDescendants()) do main(v) end
         for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do main(v) end
		RANKUP = bool
    end)








            
            
            
            local page2 = venyx:addPage("Local Player", 5012544693)
            local Farm = page2:addSection("Local Player")
    
            local Farm = page2:addSection("Infinite Jump")
        local RANKUP
        Farm:addToggle("Inf Jump", nil, function(bool)
            game:GetService("UserInputService").JumpRequest:connect(function()
                game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")      
            end)
            RANKUP = bool
        end)
    
    
    
    
    
        local Farm = page2:addSection("Anti-Afk")
        local RANKUP
        Farm:addToggle("Anti-Afk", nil, function(bool)
            wait(0.5)local ba=Instance.new("ScreenGui")
            local ca=Instance.new("TextLabel")local da=Instance.new("Frame")
            local _b=Instance.new("TextLabel")local ab=Instance.new("TextLabel")ba.Parent=game.CoreGui
            ba.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;ca.Parent=ba;ca.Active=true
            ca.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ca.Draggable=true
            ca.Position=UDim2.new(0.698610067,0,0.098096624,0)ca.Size=UDim2.new(0,304,0,52)
            ca.Font=Enum.Font.SourceSansSemibold;ca.Text="Anti Afk Kick Script"ca.TextColor3=Color3.new(0,1,1)
            ca.TextSize=22;da.Parent=ca
            da.BackgroundColor3=Color3.new(0.196078,0.196078,0.196078)da.Position=UDim2.new(0,0,1.0192306,0)
            da.Size=UDim2.new(0,304,0,107)_b.Parent=da
            _b.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)_b.Position=UDim2.new(0,0,0.800455689,0)
            _b.Size=UDim2.new(0,304,0,21)_b.Font=Enum.Font.Arial;_b.Text="Made by: RealLeon#0005"
            _b.TextColor3=Color3.new(1,1,1)_b.TextSize=20;ab.Parent=da
            ab.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ab.Position=UDim2.new(0,0,0.158377379,0)
            ab.Size=UDim2.new(0,304,0,44)ab.Font=Enum.Font.ArialBold;ab.Text="Status: Script Started"
            ab.TextColor3=Color3.new(1,1,1)ab.TextSize=20;local bb=game:service'VirtualUser'
            game:service'Players'.LocalPlayer.Idled:connect(function()
            bb:CaptureController()bb:ClickButton2(Vector2.new())
            ab.Text="You went idle and ROBLOX tried to kick you but we reflected it!"wait(2)ab.Text="Script Re-Enabled"end)
            RANKUP = bool
        end)
    
    
    
        local Farm = page2:addSection("Fly with (E)")
        local RANKUP
        Farm:addToggle("Fly (E)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/7rXZ9VNc", true))()
            RANKUP = bool
        end)
    
    



        local Title = page2:addSection("Reset Character")
    
    
        Title:addButton("Reset", function()
            game.Players.LocalPlayer.Character.Head:Remove()
        end)
    
    



    
    
        local Farm = page2:addSection("Noclip with (R)")
        local RANKUP
        Farm:addToggle("Noclip (R)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/2pwTjwS4", true))()		
            RANKUP = bool
        end)
    
    
    



        local Farm = page2:addSection("God Mode")
        local RANKUP
        Farm:addToggle("God Mode", nil, function(bool)
            loadstring(game:HttpGet(('https://raw.githubusercontent.com/Cesare0328/my-scripts/main/Mad%20City%20GodMode'),true))()
            RANKUP = bool
        end)


    
    
    
        local Farm = page2:addSection("Alt Delete")
        local RANKUP
        Farm:addToggle("Alt Delet", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/DThr62Cn", true))()		
            RANKUP = bool
        end)
    
    
    
    
        local Farm = page2:addSection("Ctrl Teleport")
        local RANKUP
        Farm:addToggle("Ctrl Teleport", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/gp9y2Wht", true))()	
            RANKUP = bool
        end)
    
    
    
        local Farm = page2:addSection("God Mode")
        local RANKUP
        Farm:addToggle("God Mode", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/MSZAznxp", true))()
            RANKUP = bool
        end)
















            local page5 = venyx:addPage("Credits", 5012544693)
            local Discord = page5:addSection("Discord")
            
            
            Discord:addButton("Copy Discord Link", function()
                setclipboard("https://discord.gg/F6dSgpUPBG")
            end)
            local Discord = page5:addSection("Credits")
            local d = page5:addSection("Made by: Leon💙#0005")
            local d = page5:addSection("Scripter: Leon💙#0005")
            local d = page5:addSection("Script Developers: /Leon💙#0005/Yomama#0001/NezyGhoul#8130/")
        
        
        
        
        
        
        
            -- themes
            local themes = {
                Background = Color3.fromRGB(24, 24, 24),
                Glow = Color3.fromRGB(0, 0, 0),
                Accent = Color3.fromRGB(10, 10, 10),
                LightContrast = Color3.fromRGB(20, 20, 20),
                DarkContrast = Color3.fromRGB(14, 14, 14),
                TextColor = Color3.fromRGB(255, 255, 255)
                }
                
                    
                -- Theme page
                local settings = venyx:addPage("Settings", 5012544693)
                local colors = settings:addSection("Colors")
                local setting = settings:addSection("Settings")
                
                setting:addKeybind("Show/Hide Settings", Enum.KeyCode.P, function()
                print("Activated Keybind")
                venyx:toggle()
                end, function()
                print("Changed Keybind")
                end)
                
                for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
                colors:addColorPicker(theme, color, function(color3)
                venyx:setTheme(theme, color3)
                end)
                end
            
            
            
            
            
            
            
            
            
            
            
            -- load
                venyx:SelectPage(venyx.pages[1], true) -- no default for more freedom
                end




















































 







                if game.PlaceId == 4924922222 then
                    local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))() --someone reuploaded it so I put it in place of the original back up so guy can get free credit.
                    local venyx = library.new("Glurak Hub: Brookhaven", 5013109572)










                    local page4 = venyx:addPage("Main", 5012544693)
                    local Farm = page4:addSection("RP Fly All")
                    

                    local RANKUP
                    Farm:addToggle("RP Fly All", nil, function(bool)
                        _G.Fly = true -- On Switch
                    Players = game:GetService("Players")
                    while _G.Fly and wait() do
                       for i, all in pairs(Players:GetPlayers()) do
                    local args = {
                       [1] = "DropButtonStopAll",
                       [2] = game:GetService("Players")[all.name]
                    }
                    
                    game:GetService("ReplicatedStorage").RemoteEvents.PlayerTriggerEvent:FireServer(unpack(args))
                    end
                    end
                        RANKUP = bool
                    end)
                
    





                    local Farm = page4:addSection("RP Kill All")
                    local RANKUP
    Farm:addToggle("RP Instant Kill All", nil, function(bool)
        Players = game:GetService("Players")
game.Players.LocalPlayer.Character.Head:Destroy()
for i, all in pairs(Players:GetPlayers()) do
local args = {
   [1] = "Client2Client",
   [2] = "Request: Piggyback!",
   [3] = game:GetService("Players")[all.name]
}
game:GetService("ReplicatedStorage").RemoteEvents.PlayerTriggerEvent:FireServer(unpack(args))
local args = {
   [1] = "BothWantPiggyBackRide",
  [2] = game:GetService("Players")[all.name]
}
game:GetService("ReplicatedStorage").RemoteEvents.PlayerTriggerEvent:FireServer(unpack(args))
end
		RANKUP = bool
    end)








    local Farm = page4:addSection("RP Teleport All Players")
    local RANKUP
    Farm:addToggle("Teleport all Players", nil, function(bool)
        Players = game:GetService("Players")
for i, all in pairs(Players:GetPlayers()) do
local args = {
   [1] = "Client2Client",
   [2] = "Request: Carry!",
   [3] = game:GetService("Players")[all.name]
}
game:GetService("ReplicatedStorage").RemoteEvents.PlayerTriggerEvent:FireServer(unpack(args))
local args = {
   [1] = "BothWantCarryHurt",
   [2] = game:GetService("Players")[all.name]
}
game:GetService("ReplicatedStorage").RemoteEvents.PlayerTriggerEvent:FireServer(unpack(args))
end

_G.Jump = true
if _G.Jump then
for i, all in pairs(Players:GetPlayers()) do
   wait(1)
   for i = 1,18 do -- 18 Player Max in the server
local args = {
   [1] = "DropButtonStopAll",
   [2] = game:GetService("Players")[all.name]
}

game:GetService("ReplicatedStorage").RemoteEvents.PlayerTriggerEvent:FireServer(unpack(args))
end
end
end
		RANKUP = bool
    end)











                    local page7 = venyx:addPage("Visual", 5012544693)
                    local Farm = page7:addSection("Visual")

                    
local Title = page7:addSection("Crash/Lag Server")
    
    
Title:addButton("Crash/Lag Server", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/racemodex/my-scripts/master/BrookhavenCrashServer", true))()
end)




local Title = page7:addSection("Item Spamm")
local RANKUP
    Farm:addToggle("Item Spamm", nil, function(bool)
        while wait() do
            local args = {
               [1] = "PickingTools",
               [2] = "SWATShield"
            }
            
            game:GetService("ReplicatedStorage").RemoteEvents.Tools:InvokeServer(unpack(args))
            
            local args = {
               [1] = "PickingTools",
               [2] = "Taser"
            }
            
            game:GetService("ReplicatedStorage").RemoteEvents.Tools:InvokeServer(unpack(args))
            
            for _,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
            game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
            v.Handle.Mesh:Destroy()
            v.Parent = workspace
            end
            end
		RANKUP = bool
    end)












                    local page2 = venyx:addPage("Local Player", 5012544693)
            local Farm = page2:addSection("Local Player")
    

    
            local Farm = page2:addSection("Infinite Jump")
        local RANKUP
        Farm:addToggle("Inf Jump", nil, function(bool)
            game:GetService("UserInputService").JumpRequest:connect(function()
                game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")      
            end)
            RANKUP = bool
        end)
    
    
    
    
    
        local Farm = page2:addSection("Anti-Afk")
        local RANKUP
        Farm:addToggle("Anti-Afk", nil, function(bool)
            wait(0.5)local ba=Instance.new("ScreenGui")
            local ca=Instance.new("TextLabel")local da=Instance.new("Frame")
            local _b=Instance.new("TextLabel")local ab=Instance.new("TextLabel")ba.Parent=game.CoreGui
            ba.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;ca.Parent=ba;ca.Active=true
            ca.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ca.Draggable=true
            ca.Position=UDim2.new(0.698610067,0,0.098096624,0)ca.Size=UDim2.new(0,304,0,52)
            ca.Font=Enum.Font.SourceSansSemibold;ca.Text="Anti Afk Kick Script"ca.TextColor3=Color3.new(0,1,1)
            ca.TextSize=22;da.Parent=ca
            da.BackgroundColor3=Color3.new(0.196078,0.196078,0.196078)da.Position=UDim2.new(0,0,1.0192306,0)
            da.Size=UDim2.new(0,304,0,107)_b.Parent=da
            _b.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)_b.Position=UDim2.new(0,0,0.800455689,0)
            _b.Size=UDim2.new(0,304,0,21)_b.Font=Enum.Font.Arial;_b.Text="Made by: RealLeon#0005"
            _b.TextColor3=Color3.new(1,1,1)_b.TextSize=20;ab.Parent=da
            ab.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ab.Position=UDim2.new(0,0,0.158377379,0)
            ab.Size=UDim2.new(0,304,0,44)ab.Font=Enum.Font.ArialBold;ab.Text="Status: Script Started"
            ab.TextColor3=Color3.new(1,1,1)ab.TextSize=20;local bb=game:service'VirtualUser'
            game:service'Players'.LocalPlayer.Idled:connect(function()
            bb:CaptureController()bb:ClickButton2(Vector2.new())
            ab.Text="You went idle and ROBLOX tried to kick you but we reflected it!"wait(2)ab.Text="Script Re-Enabled"end)
            RANKUP = bool
        end)
    
    
    
        local Farm = page2:addSection("Fly with (E)")
        local RANKUP
        Farm:addToggle("Fly (E)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/7rXZ9VNc", true))()
            RANKUP = bool
        end)
    
    



        local Title = page2:addSection("Reset Character")
    
    
        Title:addButton("Reset", function()
            game.Players.LocalPlayer.Character.Head:Remove()
        end)
    
    



    
    
        local Farm = page2:addSection("Noclip with (R)")
        local RANKUP
        Farm:addToggle("Noclip (R)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/2pwTjwS4", true))()		
            RANKUP = bool
        end)
    



    
    
    
        local Farm = page2:addSection("Alt Delete")
        local RANKUP
        Farm:addToggle("Alt Delet", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/DThr62Cn", true))()		
            RANKUP = bool
        end)
    
    
    
    
        local Farm = page2:addSection("Ctrl Teleport")
        local RANKUP
        Farm:addToggle("Ctrl Teleport", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/gp9y2Wht", true))()	
            RANKUP = bool
        end)
    
    
    
        local Farm = page2:addSection("God Mode")
        local RANKUP
        Farm:addToggle("God Mode", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/MSZAznxp", true))()
            RANKUP = bool
        end)
















            local page5 = venyx:addPage("Credits", 5012544693)
            local Discord = page5:addSection("Discord")
            
            
            Discord:addButton("Copy Discord Link", function()
                setclipboard("https://discord.gg/F6dSgpUPBG")
            end)
            local Discord = page5:addSection("Credits")
            local d = page5:addSection("Made by: Leon💙#0005")
            local d = page5:addSection("Scripter: Leon💙#0005")
            local d = page5:addSection("Script Developers: /RealLeon#0005/Yomama#0001/NezyGhoul#8130/")
        
        
        
        
        
        
        
            -- themes
            local themes = {
                Background = Color3.fromRGB(24, 24, 24),
                Glow = Color3.fromRGB(0, 0, 0),
                Accent = Color3.fromRGB(10, 10, 10),
                LightContrast = Color3.fromRGB(20, 20, 20),
                DarkContrast = Color3.fromRGB(14, 14, 14),
                TextColor = Color3.fromRGB(255, 255, 255)
                }
                
                    
                -- Theme page
                local settings = venyx:addPage("Settings", 5012544693)
                local colors = settings:addSection("Colors")
                local setting = settings:addSection("Settings")
                
                setting:addKeybind("Show/Hide Settings", Enum.KeyCode.P, function()
                print("Activated Keybind")
                venyx:toggle()
                end, function()
                print("Changed Keybind")
                end)
                
                for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
                colors:addColorPicker(theme, color, function(color3)
                venyx:setTheme(theme, color3)
                end)
                end
            
            
            
            
            
            
            
            
            
            
            
            -- load
                venyx:SelectPage(venyx.pages[1], true) -- no default for more freedom
                end



























































                if game.PlaceId == 3101667897 then
                    local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))() --someone reuploaded it so I put it in place of the original back up so guy can get free credit.
                    local venyx = library.new("Glurak Hub: Legends Of Speed", 5013109572)









                   
                    local page2 = venyx:addPage("AutoFarm", 5012544693)
                    local Farm = page2:addSection("Speed and Level Farm")
local RANKUP
    Farm:addToggle("AutoFarm", nil, function(bool)
        while wait(0.1) do
            local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3)
            end
             
            while wait(0.1) do
            local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3)
            end
             
            while wait(0.1) do
            local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3)
            end
             
            while wait(0.1) do
            local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3)
            end
             
            while wait(0.1) do
            local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Gem" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Yellow Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Orange Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3) local A_1 = "collectOrb" local A_2 = "Blue Orb" local A_3 = "City" local Event = game:GetService("ReplicatedStorage").rEvents.orbEvent Event:FireServer(A_1, A_2, A_3)
            end
		RANKUP = bool
    end)













                    local page2 = venyx:addPage("Esp", 5012544693)
                    
                    local Farm = page2:addSection("Player Esp")
                    local RANKUP
                    Farm:addToggle("Esp", nil, function(bool)
                        local MainParent = game.workspace.Terrain or nil
local LineFrame = Instance.new("ScreenGui",MainParent)
LineFrame.Name = "Lines"
LineFrame.Enabled = false
ToggleKey = Enum.KeyCode.F1
local Spotted = {};
local CharacterMotors = {}
CharacterMotors.GetMotors = function(char)
    local Motors = {}
        for i,v in pairs(char:GetDescendants()) do
            if v:IsA("Motor6D") then
                if v.Part0 and v.Part1 then--and v.Part0.Name ~= "HumanoidRootPart" and v.Part1.Name ~= "HumanoidRootPart" then
                    table.insert(Motors,{v.Part0,v.Part1})
                end
            end
        end
    table.insert(Motors,{char:FindFirstChild("Head") or char.PrimaryPart,"Camera"})
    CharacterMotors[char] = Motors
    return CharacterMotors[char]
end
        
lerp = function(a, b, t)
    return a + (b - a) * t
end
 
local ESP = {Characters = {}}
ESP.Visible = true
ESP.Init = function(char,plr)
    --if (game:GetService("Players").LocalPlayer.Team == nil or plr.Team ~= game:GetService("Players").LocalPlayer.Team) then
        char.DescendantAdded:Connect(function()
            CharacterMotors.GetMotors(char)
        end)
        
        local BillboardUi = Instance.new("BillboardGui")
        BillboardUi.AlwaysOnTop = true
        BillboardUi.Size = UDim2.new(3,60,1,30)
        BillboardUi.StudsOffsetWorldSpace = Vector3.new(0,-4.5,0)
        BillboardUi.Adornee = char:WaitForChild("HumanoidRootPart")
        
        local PlayerName = Instance.new("TextLabel",BillboardUi)
        PlayerName.BackgroundTransparency = 1
        PlayerName.TextColor3 = (game:GetService("Players"):GetPlayerFromCharacter(char)).TeamColor.Color
        PlayerName.Size = UDim2.new(1,0,.3,0)
        PlayerName.ZIndex = 2
        PlayerName.Text = char.Name
        PlayerName.TextScaled = true
        PlayerName.TextStrokeTransparency = .25
        PlayerName.Font = Enum.Font.GothamBold
        PlayerName.TextStrokeColor3 = Color3.fromRGB(33, 33, 33)
        
        local Distance = PlayerName:Clone()
        Distance.Parent = BillboardUi
        Distance.Font = Enum.Font.Gotham
        Distance.TextColor3 = Color3.new(1,1,1)
        Distance.Position = UDim2.new(0,0,.3,0)
        
        local Health = PlayerName:Clone()
        Health.Parent = BillboardUi
        Health.Font = Enum.Font.Gotham
        Health.Position = UDim2.new(0,0,.6,0)
        
        ESP.Characters[char] = {PlayerName,Distance,Health,BillboardUi}
    --end
end
ESP.Render = function()
    
    for i,v in pairs(ESP.Characters) do
        pcall(function()
            local shrink = ((((game.Workspace.CurrentCamera.CFrame.p) - i.HumanoidRootPart.Position).Magnitude)/1500)+1
            v[2].Text = math.floor(((game.Workspace.CurrentCamera.CFrame.p) - i.HumanoidRootPart.Position).Magnitude+.5)
            v[3].Text = math.floor(i.Humanoid.Health).."/"..i.Humanoid.MaxHealth.." - "..math.floor(((i.Humanoid.Health/i.Humanoid.MaxHealth)*100)+.5).."%"
            v[3].TextColor3 = Color3.fromHSV((i.Humanoid.Health/i.Humanoid.MaxHealth) * (80/255),1,1)
            if not Spotted[i] then
                --v[1].TextTransparency = lerp(v[1].TextTransparency,.6,0.05)
            else
                --v[1].TextTransparency = lerp(v[1].TextTransparency,0,0.1)
            end
            v[1].TextColor3 = (game:GetService("Players"):GetPlayerFromCharacter(i)).TeamColor.Color
            --v[1].TextStrokeTransparency = 1-((1-v[1].TextTransparency)/2)
            --v[2].TextTransparency = v[1].TextTransparency
            --v[2].TextStrokeTransparency = v[1].TextStrokeTransparency
            --v[3].TextTransparency = v[1].TextTransparency
            --v[3].TextStrokeTransparency = v[1].TextStrokeTransparency
            v[4].Size = UDim2.new(3,60/shrink,1,30/shrink)
            v[1].Visible = ESP.Visible
            v[2].Visible = ESP.Visible
            v[3].Visible = ESP.Visible
            v[4].Parent = MainParent
            
        end)
    end
    
end
 
local Perspective = {}
Perspective.CalculatePoint = function(position,cam)
    local vector, onScreen = cam:WorldToScreenPoint(position)
    return Vector2.new(vector.X, vector.Y),vector.Z,onScreen
end
 
local Draw = {UsedLines = {}}
Draw.Line = function(a,b,line,width)
    if a and b then 
        local lerp = a:Lerp(b,.5)
        local Magnitude = (a-b).Magnitude
        line.AnchorPoint = Vector2.new(0.5,.5)
        line.Position = UDim2.new(lerp.X/game.Workspace.CurrentCamera.ViewportSize.X,0,(lerp.Y/(game.Workspace.CurrentCamera.ViewportSize.Y-36)),36/2)
        line.Size = UDim2.new(Magnitude/line.Parent.AbsoluteSize.X,0,0,width)
        line.Rotation = math.deg(math.atan2(a.y - b.y, a.x - b.x))
    else
        line:Destroy()
    end
end
 
 
Draw.Character = function(player,lines,cam)
    local Motors = CharacterMotors[player]
    if not Motors then
        Motors = CharacterMotors.GetMotors(player)
    end
 
    for i,v in pairs(Motors) do
        if v[1] and v[2] then
            local FoundLine = nil
            for i,v in pairs(lines:GetChildren()) do
                if Draw.UsedLines[v] == nil then
                    Draw.UsedLines[v] = true
                    FoundLine = v
                    break
                end
            end
            local a2d,az,screen = Perspective.CalculatePoint(v[1].Position,cam)
            local b2d,bz,screen2
            local v2pos = v[2].Position
            Spotted[player] = false
            if v[2] == "Camera" then
                local ray = Ray.new(v[1].Position, (cam.CFrame.p - v[1].Position).unit * (cam.CFrame.p - v[1].Position).Magnitude)
                local part, position = workspace:FindPartOnRayWithIgnoreList(ray, {game:GetService("Players").LocalPlayer.Character,player}, false, true)
                if part then
                    screen = false
                    screen2 = false
                else
                    Spotted[player] = true
                    b2d,bz,screen2 = Vector2.new(cam.ViewportSize.x/2, cam.ViewportSize.y),0,true   
                    screen = true
                end
                v2pos = v[1].Position
            else
                b2d,bz,screen2 = Perspective.CalculatePoint(v[2].Position,cam)  
            end
            if screen and screen2 and (v[1].Position-v2pos).Magnitude <= 5 then
                if not FoundLine then
                    FoundLine = Instance.new("Frame")
                    FoundLine.BackgroundColor3 = Color3.new(1,1,1)
                    FoundLine.BackgroundTransparency = .25
                    FoundLine.BorderSizePixel = 0
                    FoundLine.Parent = lines    
                    Draw.UsedLines[FoundLine] = true
                end
                if screen then
                    Draw.Line(a2d,b2d,FoundLine,1)
                else
                    Draw.Line(b2d,a2d,FoundLine,1)
                end
            elseif FoundLine then
                FoundLine:Destroy()
            end
        end
    end
end
 
Draw.ResetLines = function(lines)
    for i,v in pairs(lines:GetChildren()) do
        if Draw.UsedLines[v] == nil then
            v:Destroy()
        end
    end
    Draw.UsedLines = {}
end
 
local AddPlayer = function(plr)
    coroutine.resume(coroutine.create(function()
        if plr ~= game:GetService("Players").LocalPlayer  then
            if plr.Character then
                ESP.Init(plr.Character,plr)
            end
            plr.CharacterAdded:Connect(function(cha)
                ESP.Init(cha,plr)
            end)
        end
    end))
end
 
for i,v in pairs(game:GetService("Players"):GetChildren()) do
    AddPlayer(v)
end
game:GetService("Players").PlayerAdded:Connect(function(v)
    AddPlayer(v)
end)
game:GetService("UserInputService").InputBegan:connect(function(inputObject)
    if inputObject.KeyCode == ToggleKey then
        ESP.Visible = not ESP.Visible
    end
end)
game:GetService("RunService").RenderStepped:Connect(function()
    ESP.Render()
    for i,v in pairs(game:GetService("Players"):GetChildren()) do
        if v.Character and v ~= game:GetService("Players").LocalPlayer and (game:GetService("Players").LocalPlayer.Team == nil or v.Team ~= game:GetService("Players").LocalPlayer.Team) then
            if v.Character.PrimaryPart and (v.Character.PrimaryPart.Position - game.Workspace.CurrentCamera.CFrame.Position).Magnitude <= 200 then
                Draw.Character(v.Character,LineFrame,game.Workspace.CurrentCamera)
            end
        end
    end
    Draw.ResetLines(LineFrame)
end)

                        RANKUP = bool
                    end)
                
                
                
                
















                    local page2 = venyx:addPage("Local Player", 5012544693)
            local Farm = page2:addSection("Local Player")
    

    
            local Farm = page2:addSection("Infinite Jump")
        local RANKUP
        Farm:addToggle("Inf Jump", nil, function(bool)
            game:GetService("UserInputService").JumpRequest:connect(function()
                game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")      
            end)
            RANKUP = bool
        end)
    
    
    
    
    
        local Farm = page2:addSection("Anti-Afk")
        local RANKUP
        Farm:addToggle("Anti-Afk", nil, function(bool)
            wait(0.5)local ba=Instance.new("ScreenGui")
            local ca=Instance.new("TextLabel")local da=Instance.new("Frame")
            local _b=Instance.new("TextLabel")local ab=Instance.new("TextLabel")ba.Parent=game.CoreGui
            ba.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;ca.Parent=ba;ca.Active=true
            ca.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ca.Draggable=true
            ca.Position=UDim2.new(0.698610067,0,0.098096624,0)ca.Size=UDim2.new(0,304,0,52)
            ca.Font=Enum.Font.SourceSansSemibold;ca.Text="Anti Afk Kick Script"ca.TextColor3=Color3.new(0,1,1)
            ca.TextSize=22;da.Parent=ca
            da.BackgroundColor3=Color3.new(0.196078,0.196078,0.196078)da.Position=UDim2.new(0,0,1.0192306,0)
            da.Size=UDim2.new(0,304,0,107)_b.Parent=da
            _b.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)_b.Position=UDim2.new(0,0,0.800455689,0)
            _b.Size=UDim2.new(0,304,0,21)_b.Font=Enum.Font.Arial;_b.Text="Made by: RealLeon#0005"
            _b.TextColor3=Color3.new(1,1,1)_b.TextSize=20;ab.Parent=da
            ab.BackgroundColor3=Color3.new(0.176471,0.176471,0.176471)ab.Position=UDim2.new(0,0,0.158377379,0)
            ab.Size=UDim2.new(0,304,0,44)ab.Font=Enum.Font.ArialBold;ab.Text="Status: Script Started"
            ab.TextColor3=Color3.new(1,1,1)ab.TextSize=20;local bb=game:service'VirtualUser'
            game:service'Players'.LocalPlayer.Idled:connect(function()
            bb:CaptureController()bb:ClickButton2(Vector2.new())
            ab.Text="You went idle and ROBLOX tried to kick you but we reflected it!"wait(2)ab.Text="Script Re-Enabled"end)
            RANKUP = bool
        end)
    
    
    
        local Farm = page2:addSection("Fly with (E)")
        local RANKUP
        Farm:addToggle("Fly (E)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/7rXZ9VNc", true))()
            RANKUP = bool
        end)
    
    



        local Title = page2:addSection("Reset Character")
    
    
        Title:addButton("Reset", function()
            game.Players.LocalPlayer.Character.Head:Remove()
        end)
    
    



    
    
        local Farm = page2:addSection("Noclip with (R)")
        local RANKUP
        Farm:addToggle("Noclip (R)", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/2pwTjwS4", true))()		
            RANKUP = bool
        end)
    



    
    
    
        local Farm = page2:addSection("Alt Delete")
        local RANKUP
        Farm:addToggle("Alt Delet", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/DThr62Cn", true))()		
            RANKUP = bool
        end)
    
    
    
    
        local Farm = page2:addSection("Ctrl Teleport")
        local RANKUP
        Farm:addToggle("Ctrl Teleport", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/gp9y2Wht", true))()	
            RANKUP = bool
        end)
    
    
    
        local Farm = page2:addSection("God Mode")
        local RANKUP
        Farm:addToggle("God Mode", nil, function(bool)
            loadstring(game:HttpGet("https://pastebin.com/raw/MSZAznxp", true))()
            RANKUP = bool
        end)
















            local page5 = venyx:addPage("Credits", 5012544693)
            local Discord = page5:addSection("Discord")
            
            
            Discord:addButton("Copy Discord Link", function()
                setclipboard("https://discord.gg/F6dSgpUPBG")
            end)
            local Discord = page5:addSection("Credits")
            local d = page5:addSection("Made by: Leon💙#0005")
            local d = page5:addSection("Scripter: Leon💙#0005")
            local d = page5:addSection("Script Developers: /RealLeon#0005/Yomama#0001/NezyGhoul#8130/")
        
        
        
        
        
        
        
            -- themes
            local themes = {
                Background = Color3.fromRGB(24, 24, 24),
                Glow = Color3.fromRGB(0, 0, 0),
                Accent = Color3.fromRGB(10, 10, 10),
                LightContrast = Color3.fromRGB(20, 20, 20),
                DarkContrast = Color3.fromRGB(14, 14, 14),
                TextColor = Color3.fromRGB(255, 255, 255)
                }
                
                    
                -- Theme page
                local settings = venyx:addPage("Settings", 5012544693)
                local colors = settings:addSection("Colors")
                local setting = settings:addSection("Settings")
                
                setting:addKeybind("Show/Hide Settings", Enum.KeyCode.P, function()
                print("Activated Keybind")
                venyx:toggle()
                end, function()
                print("Changed Keybind")
                end)
                
                for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
                colors:addColorPicker(theme, color, function(color3)
                venyx:setTheme(theme, color3)
                end)
                end
            
            
            
            
            
            
            
            
            
            
            
            -- load
                venyx:SelectPage(venyx.pages[1], true) -- no default for more freedom
                end





