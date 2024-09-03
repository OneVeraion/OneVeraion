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
    Name = "ហោះ",
    Callback = function()
        loadstring("\108\111\97\100\115\116\114\105\110\103\40\103\97\109\101\58\72\116\116\112\71\101\116\40\40\39\104\116\116\112\115\58\47\47\103\105\115\116\46\103\105\116\104\117\98\117\115\101\114\99\111\110\116\101\110\116\46\99\111\109\47\109\101\111\122\111\110\101\89\84\47\98\102\48\51\55\100\102\102\57\102\48\97\55\48\48\49\55\51\48\52\100\100\100\54\55\102\100\99\100\51\55\48\47\114\97\119\47\101\49\52\101\55\52\102\52\50\53\98\48\54\48\100\102\53\50\51\51\52\51\99\102\51\48\98\55\56\55\48\55\52\101\98\51\99\53\100\50\47\97\114\99\101\117\115\37\50\53\50\48\120\37\50\53\50\48\102\108\121\37\50\53\50\48\50\37\50\53\50\48\111\98\102\108\117\99\97\116\111\114\39\41\44\116\114\117\101\41\41\40\41\10\10")()
    end    
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

Tab1:AddButton({
    Name = "បំបាត់អាប់",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-better-shaders-17164"))()
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
