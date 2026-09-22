local CoreGui = game:GetService("CoreGui")
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local LocalPlayer = Players.LocalPlayer

_G.AutoFarm = false

local CommF = ReplicatedStorage:WaitForChild("Remotes"):WaitForChild("CommF_")

local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "GodusHub_TabMenu"
ScreenGui.Parent = CoreGui

local ToggleButton = Instance.new("TextButton")
ToggleButton.Size = UDim2.new(0, 50, 0, 50)
ToggleButton.Position = UDim2.new(0.05, 0, 0.1, 0)
ToggleButton.Text = "HUB"
ToggleButton.TextSize = 14
ToggleButton.Font = Enum.Font.GothamBold
ToggleButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
ToggleButton.TextColor3 = Color3.fromRGB(255, 150, 0)
ToggleButton.Parent = ScreenGui

local ToggleCorner = Instance.new("UICorner")
ToggleCorner.CornerRadius = UDim.new(0, 12)
ToggleCorner.Parent = ToggleButton

local MainFrame = Instance.new("Frame")
MainFrame.Size = UDim2.new(0, 450, 0, 300)
MainFrame.Position = UDim2.new(0.3, 0, 0.3, 0)
MainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
MainFrame.Visible = false
MainFrame.Parent = ScreenGui

local MainCorner = Instance.new("UICorner")
MainCorner.CornerRadius = UDim.new(0, 10)
MainCorner.Parent = MainFrame

local MainStroke = Instance.new("UIStroke")
MainStroke.Thickness = 2
MainStroke.Color = Color3.fromRGB(255, 100, 0)
MainStroke.Parent = MainFrame

ToggleButton.MouseButton1Click:Connect(function()
    MainFrame.Visible = not MainFrame.Visible
end)

local TitleLabel = Instance.new("TextLabel")
TitleLabel.Size = UDim2.new(1, 0, 0, 40)
TitleLabel.Position = UDim2.new(0, 0, 0, 0)
TitleLabel.Text = "  GODUS HUB | Blox Fruits"
TitleLabel.TextSize = 14
TitleLabel.Font = Enum.Font.GothamBold
TitleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TitleLabel.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
TitleLabel.Parent = MainFrame

local TitleCorner = Instance.new("UICorner")
TitleCorner.CornerRadius = UDim.new(0, 10)
TitleCorner.Parent = TitleLabel

local TabBar = Instance.new("Frame")
TabBar.Size = UDim2.new(0, 120, 1, -45)
TabBar.Position = UDim2.new(0, 0, 0, 45)
TabBar.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
TabBar.Parent = MainFrame

local FarmTabButton = Instance.new("TextButton")
FarmTabButton.Size = UDim2.new(1, -10, 0, 35)
FarmTabButton.Position = UDim2.new(0, 5, 0, 10)
FarmTabButton.Text = "Auto Farm"
FarmTabButton.TextSize = 12
FarmTabButton.Font = Enum.Font.GothamBold
FarmTabButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
FarmTabButton.TextColor3 = Color3.fromRGB(255, 255, 255)
FarmTabButton.Parent = TabBar

local FarmCorner = Instance.new("UICorner")
FarmCorner.CornerRadius = UDim.new(0, 6)
FarmCorner.Parent = FarmTabButton

local MiscTabButton = Instance.new("TextButton")
MiscTabButton.Size = UDim2.new(1, -10, 0, 35)
MiscTabButton.Position = UDim2.new(0, 5, 0, 55)
MiscTabButton.Text = "Settings"
MiscTabButton.TextSize = 12
MiscTabButton.Font = Enum.Font.GothamBold
MiscTabButton.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
MiscTabButton.TextColor3 = Color3.fromRGB(150, 150, 150)
MiscTabButton.Parent = TabBar

local MiscCorner = Instance.new("UICorner")
MiscCorner.CornerRadius = UDim.new(0, 6)
MiscCorner.Parent = MiscTabButton

local FarmContainer = Instance.new("Frame")
FarmContainer.Size = UDim2.new(1, -130, 1, -55)
FarmContainer.Position = UDim2.new(0, 125, 0, 50)
FarmContainer.BackgroundTransparency = 1
FarmContainer.Visible = true
FarmContainer.Parent = MainFrame

local MiscContainer = Instance.new("Frame")
MiscContainer.Size = UDim2.new(1, -130, 1, -55)
MiscContainer.Position = UDim2.new(0, 125, 0, 50)
MiscContainer.BackgroundTransparency = 1
MiscContainer.Visible = false
MiscContainer.Parent = MainFrame

FarmTabButton.MouseButton1Click:Connect(function()
    FarmContainer.Visible = true
    MiscContainer.Visible = false
    FarmTabButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
    FarmTabButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    MiscTabButton.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
    MiscTabButton.TextColor3 = Color3.fromRGB(150, 150, 150)
end)

MiscTabButton.MouseButton1Click:Connect(function()
    FarmContainer.Visible = false
    MiscContainer.Visible = true
    MiscTabButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
    MiscTabButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    FarmTabButton.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
    FarmTabButton.TextColor3 = Color3.fromRGB(150, 150, 150)
end)

local FarmToggleBtn = Instance.new("TextButton")
FarmToggleBtn.Size = UDim2.new(0, 200, 0, 40)
FarmToggleBtn.Position = UDim2.new(0, 10, 0, 10)
FarmToggleBtn.Text = "Auto Farm + Quest: OFF"
FarmToggleBtn.TextSize = 12
FarmToggleBtn.Font = Enum.Font.GothamBold
FarmToggleBtn.BackgroundColor3 = Color3.fromRGB(200, 50, 50)
FarmToggleBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
FarmToggleBtn.Parent = FarmContainer

local FarmBtnCorner = Instance.new("UICorner")
FarmBtnCorner.CornerRadius = UDim.new(0, 6)
FarmBtnCorner.Parent = FarmToggleBtn

FarmToggleBtn.MouseButton1Click:Connect(function()
    _G.AutoFarm = not _G.AutoFarm
    if _G.AutoFarm then
        FarmToggleBtn.Text = "Auto Farm + Quest: ON"
        FarmToggleBtn.BackgroundColor3 = Color3.fromRGB(50, 200, 50)
    else
        FarmToggleBtn.Text = "Auto Farm + Quest: OFF"
        FarmToggleBtn.BackgroundColor3 = Color3.fromRGB(200, 50, 50)
    end
end)

local SettingsLabel = Instance.new("TextLabel")
SettingsLabel.Size = UDim2.new(1, -20, 0, 40)
SettingsLabel.Position = UDim2.new(0, 10, 0, 10)
SettingsLabel.Text = "Additional settings such as walkspeed or UI hide."
SettingsLabel.TextSize = 12
SettingsLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
SettingsLabel.BackgroundTransparency = 1
SettingsLabel.TextWrapped = true
SettingsLabel.Parent = MiscContainer

local function CheckQuest()
    local playerGui = LocalPlayer:FindFirstChild("PlayerGui")
    if playerGui then
        local questGui = playerGui:FindFirstChild("Main") and playerGui.Main:FindFirstChild("Quest")
        if questGui and questGui.Visible == false then
            return false
        end
    end
    return true
end

task.spawn(function()
    print("---------------------------------------------")
    print("GODUS HUB (Clean Version) Initialized!")
    print("---------------------------------------------")
    
    while true do
        task.wait(1)
        if _G.AutoFarm then
            local character = LocalPlayer.Character
            if character and character:FindFirstChild("HumanoidRootPart") then
                local rootPart = character.HumanoidRootPart
                local hasQuest = CheckQuest()
                
                if not hasQuest then
                    print("[GODUS] Getting quest...")
                    rootPart.CFrame = CFrame.new(1062, 16, 1417)
                    task.wait(0.5)
                    pcall(function()
                        CommF:InvokeServer("StartQuest", "BanditQuest1", 1)
                    end)
                else
                    print("[GODUS] Farming monsters...")
                    rootPart.CFrame = CFrame.new(1150, 40, 1650)
                    pcall(function()
                        CommF:InvokeServer("UseAbility", "Melee")
                    end)
                end
            end
        end
    end
end)
