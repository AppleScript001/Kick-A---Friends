local Material = loadstring(game:HttpGet("https://raw.githubusercontent.com/Kinlei/MaterialLua/master/Module.lua"))()
repeat wait() until game:IsLoaded()
game:GetService("Players").LocalPlayer.Idled:connect(function()
game:GetService("VirtualUser"):ClickButton2(Vector2.new())
end)
local X = Material.Load({
Title = "🏋️ Kick A Friend 🥊",
Style = 2,
SizeX = 320,
SizeY = 320,
Theme = "Dark",
ColorOverrides = {
MainFrame = Color3.fromRGB(0,9,55)
}
})
local Y = X.New({
Title = "Main"
})
Y.Dropdown({
	Text = "Select | Train",
	Callback = function(t)
        train = t
	end,
	Options = {
			"0 Recommended",
			"125 Recommended",
			"1.5K Recommended",
			"7.5K Recommended",
			"25K Recommended",
            "50K Recommended",
            "2.5M Recommended",
            "17M Recommended",
            "125M Recommended",
            "500M Recommended",
			"2B Recommended",
            "50B Recommended",
            "290B Recommended",
            "1T Recommended",
            
	},
})
Y.Toggle({
    Text = "Auto Train-Selected",
    Callback = function(Value)
    _G.train = Value
    while _G.train do
    task.wait(0.1)
	if train == "0 Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("1")
	elseif train == "125 Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("2")
	elseif train == "1.5K Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("3")
	elseif train == "7.5K Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("4")
	elseif train == "25K Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("5")
    elseif train == "50K Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("6")
	elseif train == "2.5M Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("7")
	elseif train == "17M Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("8")
	elseif train == "125M Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("9")
	elseif train == "500M Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("10")
	elseif train == "2B Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("12")
	elseif train == "50B Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("13")
	elseif train == "290B Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("14")
	elseif train == "1T Recommended" then
		game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("TrainingService"):WaitForChild("RE"):WaitForChild("Click"):FireServer("15")
		
	end
	end
    end,
    Enabled = false
})
Y.Toggle({
    Text = "Auto Kick/Wins",
    Callback = function(Value)
    _G.Kick = Value
    while _G.Kick do
    task.wait(0.1)
	local args = {
		[1] = "4"
	}
	
	game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("KickService"):WaitForChild("RE"):WaitForChild("Start"):FireServer(unpack(args))
	wait(1)
	local args = {
		[1] = math.huge
	}
	
	game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("KickService"):WaitForChild("RE"):WaitForChild("End"):FireServer(unpack(args))	
    end
    end,
    Enabled = false
})
Y.Toggle({
    Text = "Auto Collect",
    Callback = function(Value)
    _G.Collect = Value
    while _G.Collect do
    task.wait(1)
	for _,v in pairs(workspace.GameItems.Bolts:GetDescendants()) do
		if v:IsA("TouchTransmitter") then
		firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
		firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
		end
	end
    end
    end,
    Enabled = false
})
Y.Toggle({
    Text = "Auto Rebirth",
    Callback = function(Value)
    _G.reb = Value
    while _G.reb do
    task.wait(0.1)
    game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("RebirthService"):WaitForChild("RE"):WaitForChild("Rebirth"):FireServer()
    end
    end,
    Enabled = false
})
local E = X.New({
	Title = "Pets"
})
E.Dropdown({
	Text = "Select | Eggs",
	Callback = function(t)
		Egg = t
	end,
	Options = {
			"Basic Egg",
			"Forest Egg",
			"Ninja Egg",
			"Dominus Egg",
            "Desert Egg",
            "Cactus Egg",
            "Mystic Egg",
            "Lucky Egg",
			"Atlantis Egg",
			"Kraken Egg",
			"Pirate Egg",
			
    }
})
E.Toggle({
    Text = "Auto Buy [x1]",
    Callback = function(Value)
    _G.egg = Value
    while _G.egg do
    task.wait(0.1)
	game:GetService("ReplicatedStorage"):WaitForChild("Library"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("EggService"):WaitForChild("RE"):WaitForChild("HatchEgg"):FireServer(Egg, "Single")
    end
    end,
    Enabled = false
})
