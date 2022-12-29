local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Minus Elevation GUI", "Midnight")

--MAIN
local Main = Window:NewTab("Main")
local MainSection = Main:NewSection("Scripts")
local OtherSection = Main:NewSection("Infinite Yeild")


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
