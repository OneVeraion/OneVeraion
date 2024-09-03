local player = game.Players.LocalPlayer
local OrionLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Orion/main/source'))()
local Window = OrionLib:MakeWindow({Name = "One_day and Versiom Fish Hub", HidePremium = false, SaveConfig = true, ConfigFolder = "OrionTest"})

-- Create the first tab
local Tab1 = Window:MakeTab({
    Name = "Farm",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

Tab1:AddSection({
    Name = "LocalPlayer"
})

OrionLib:MakeNotification({
    Name = "Fishing",
    Content = "Notification content... what will it say??",
    Image = "rbxassetid://4483345998",
    Time = 5
})

Tab1:AddButton({
    Name = "របស់គេ",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/haxhell/roblox-scripts/main/haxhub.lua", true))()
    end    
})

Tab1:AddButton({
    Name = "បើកហិបពេជ្យ",
    Callback = function()
        -- Define the chest's name or find it by its location
        local chestName = "Chest" -- Change this to the actual name of your chest in the Workspace

        -- Function to teleport the player
        local function teleportToChest()
            -- Get the player and their character
            local player = game.Players.LocalPlayer
            local character = player.Character
            if not character then
                warn("Character not found!")
                return
            end

            -- Find the chest in the Workspace
            local chest = workspace:FindFirstChild(chestName)
            if chest and chest:IsA("BasePart") then
                -- Move the player's character to the chest's position
                local rootPart = character:FindFirstChild("HumanoidRootPart")
                if rootPart then
                    rootPart.CFrame = chest.CFrame + Vector3.new(0, 3, 0) -- Slightly above the chest to avoid getting stuck
                else
                    warn("HumanoidRootPart not found!")
                end
            else
                warn("Chest not found or is not a BasePart!")
            end
        end

        -- Call the teleport function
        teleportToChest()
    end
})

-- Create the second tab
local Tab2 = Window:MakeTab({
    Name = "ប្ដូរទីតាំង",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

Tab2:AddButton({
    Name = "ទូកបាក់បែក",
    Callback = function()
        -- Function to teleport to ShipModel
        local function teleportToShipModel()
            for i, v in pairs(game.Workspace:GetChildren()) do
                if string.find(v.Name, "ShipModel") then
                    local hitBox = v:FindFirstChild("HitBox")
                    if hitBox and hitBox:IsA("BasePart") then
                        player.Character.HumanoidRootPart.CFrame = hitBox.CFrame
                        break
                    else
                        warn("HitBox not found or is not a BasePart!")
                    end
                end
            end
        end

        -- Call the function
        teleportToShipModel()
    end
})

-- Define the teleport function
local function teleport(cframe)
    local player = game.Players.LocalPlayer
    local character = player.Character
    if character and character:FindFirstChild("HumanoidRootPart") then
        character.HumanoidRootPart.CFrame = cframe
    else
        warn("HumanoidRootPart not found!")
    end
end

-- Add teleport buttons for specific locations
Tab2:AddButton({
    Name = "កោះកំណើត",
    Callback = function()
        teleport(CFrame.new(1.8703980445862, 53.57190322876, -188.37982177734))
    end
})

Tab2:AddButton({
    Name = "កោះព្រៃបុរាណ",
    Callback = function()
        teleport(CFrame.new(-2436.431640625, 43.564971923828, -1683.4526367188))
    end
})

Tab2:AddButton({
    Name = "កោះស្រមោល",
    Callback = function()
        teleport(CFrame.new(2196.9926757812, 43.491630554199, -2216.4543457031))
    end
})

Tab2:AddButton({
    Name = "កោះប្រាសាទ",
    Callback = function()
        teleport(CFrame.new(-4142.74609375, 46.71378326416, 262.05679321289))
    end
})

Tab2:AddButton({
    Name = "កោះភ្នំភ្លើង",
    Callback = function()
        teleport(CFrame.new(3022.9311523438, 52.347640991211, 1323.74609375))
    end
})

Tab2:AddButton({
    Name = "កោះបីសាចត្រីធំ",
    Callback = function()
        teleport(CFrame.new(-3211.9047851562, 41.850345611572, 2735.306640625))
    end
})

Tab2:AddButton({
    Name = "ទៅទូក",
    Callback = function()
        local foundBoat = false
        for i, v in pairs(game.Workspace:GetChildren()) do
            if v.Name == (game.Players.LocalPlayer.Name .. "'s Boat") then
                if player.Character and player.Character:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Controller") and v.Controller:FindFirstChild("VehicleSeat") then
                    player.Character.HumanoidRootPart.CFrame = v.Controller.VehicleSeat.CFrame + Vector3.new(0, 3, 0)
                    foundBoat = true
                    break
                else
                    warn("Controller or VehicleSeat not found!")
                end
            end
        end
        if not foundBoat then
            warn("Boat not found!")
        end
    end
})

-- Create the third tab
local Tab2 = Window:MakeTab({
    Name = "ទុកធ្វើមួយទៀត",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})
