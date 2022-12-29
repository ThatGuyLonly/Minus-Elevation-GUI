local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Minus Elevation GUI - made by new lonly#6825", "Midnight")

--MAIN
local Changelogs = Window:NewTab("Changelogs")
local Changelogs = Changelogs:NewSection("Changelogs")
local Main = Window:NewTab("Main")
local Experimental = Window:NewTab("Experimental no work")
local Experimental = Experimental:NewSection("EXPERIMENTALL")
local Player = Window:NewTab("Player")
local Player = Player:NewSection("Player")
local ESP = Window:NewTab("ESP")
local ESP = ESP:NewSection("Scripts")
local MainSection = Main:NewSection("Scripts")
local OtherSection = Main:NewSection("Infinite Yeild")

Changelogs:NewLabel("Added ESP/Chams")
Changelogs:NewLabel("Added Experimental tab")

ESP:NewButton("Button Chams", "Shows Button Locations", function()
    function update()
        for i,v in pairs(game:GetService("Workspace").Buttons:GetDescendants()) do
            if v.ClassName == "Part" and v.Name == "Button"  then
                local box = Instance.new("BoxHandleAdornment", v)
                    box.AlwaysOnTop = true
                    box.Adornee = v
                    box.Size = v.Size
                    box.Color3 = v.Color
                    box.ZIndex = 1
            end
        end
        end
        
        while wait() do
        update()
        end
end)

ESP:NewButton("Enemy Chams", "Shows enemies", function()
    function update()
        for i,v in pairs(game:GetService("Workspace").Entities:GetDescendants()) do
            if v:IsA("Part") or v:IsA("MeshPart") then
                if not v:FindFirstChild("BoxHandleAdornment") then
                    v.Transparency = 1
                    local box = Instance.new("BoxHandleAdornment", v)
                    box.AlwaysOnTop = true
                    box.Adornee = v
                    box.Size = v.Size
                    box.Color3 = Color3.fromRGB(196, 40, 28)
                    box.ZIndex = 1
                end
            end
        end
    end
        
    while wait() do
    update()
    end
end)

Experimental:NewButton("Dangerous Entity Notifications DOSENT WORK RN", "Sends a notifcation when a dangerooewruewf entitiy spawnsd", function()
    if game.workspace.Entities.Statues == true then do  
        wait(1.2)
        game.StarterGui:SetCore("SendNotification", {
        Title = "Gluttony has spawned"; -- the title (ofc)
        Text = "ruh roh"; -- what the text says (ofc) 
        Duration = 10; })
    end end
end)

--BUTTONS
MainSection:NewButton("Click All Buttons", "Clicks all buttons for you. Not fully automatic", function()
    local Buttons = workspace:WaitForChild("Buttons")
    local lp = game.Players.LocalPlayer
    local char = lp.Character

for i,v in pairs(Buttons:GetDescendants()) do
    if v and v:IsA("ProximityPrompt") and v.Name == "ButtonPrompt" and v.Parent:FindFirstChild("PointLight") and v.Parent:FindFirstChild("PointLight").Enabled == true then
        local orgpos = char.HumanoidRootPart.Position
        char.HumanoidRootPart.CFrame = CFrame.new(v.Parent.Position+Vector3.new(0,1,-1))
        wait(0.30)
        fireproximityprompt(v)
        wait(0.1)
        char.HumanoidRootPart.CFrame = CFrame.new(orgpos)
    end
end 
end)

--END ALL BUTTONS

--COLLECT ITEMS
MainSection:NewButton("Collect Items", "Dosent collect info :skull:", function()
local Items = workspace:WaitForChild("Items")
local lp = game.Players.LocalPlayer
local char = lp.Character

for i,v in pairs(Items:GetDescendants()) do
    if v and v:IsA("ProximityPrompt") and v.Name == "GrabPrompt" == true then
        local orgpos = char.HumanoidRootPart.Position
        char.HumanoidRootPart.CFrame = CFrame.new(v.Parent.Position+Vector3.new(0,1,-1))
        wait(0.30)
        fireproximityprompt(v)
        wait(0.1)
        char.HumanoidRootPart.CFrame = CFrame.new(orgpos)
    end
end    
end)
--END COLLECT ALL ITEMS i fixed it probably

MainSection:NewButton("Collect Info", "Dosent collect tiems :skull:", function()
    local Items = workspace:WaitForChild("Items")
    local lp = game.Players.LocalPlayer
    local char = lp.Character
    
    for i,v in pairs(Items:GetDescendants()) do
        if v and v:IsA("ProximityPrompt") and v.Name == "InfoPrompt" == true then
            local orgpos = char.HumanoidRootPart.Position
            char.HumanoidRootPart.CFrame = CFrame.new(v.Parent.Position+Vector3.new(0,1,-1))
            wait(0.30)
            fireproximityprompt(v)
            wait(0.1)
            char.HumanoidRootPart.CFrame = CFrame.new(orgpos)
        end
    end  
end)
--END COLLECT ALL ITEMS

--squash the funny little pumpkins
MainSection:NewButton("Squash Pumpkins", "gives you pumpkin bombs and little weird candles things or whatecver", function()
    local Items = workspace:WaitForChild("Items")
    local lp = game.Players.LocalPlayer
    local char = lp.Character
    
    for i,v in pairs(Items:GetDescendants()) do
        if v and v:IsA("ProximityPrompt") and v.Name == "ProximityPrompt" == true then
            local orgpos = char.HumanoidRootPart.Position
            char.HumanoidRootPart.CFrame = CFrame.new(v.Parent.Position+Vector3.new(0,1,-1))
            wait(0.30)
            fireproximityprompt(v)
            wait(0.1)
            char.HumanoidRootPart.CFrame = CFrame.new(orgpos)
        end
    end  
end)

--ends the little funky pumpkin thibgnor whastwqtyirfgweiyutgweiygty

OtherSection:NewButton("Infinite Yeild", "its infinite yeild", function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
end)


Player:NewSlider("Player Speed", "increases speed lmao11423213123213123123", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)

Player:NewSlider("Player Jump Power", "increases jumpoweerewtrewr lmao11423213123213123123", 250, 0, function(j) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = j
end)

Player:NewButton("Reset Player (NOT DEATH)", "Resets speed and jumpower", function()
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = 50
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 16
end)

