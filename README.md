Documentation

Installation

	local Lumina = loadstring(game:HttpGet('PUT_YOUR_RAW_URL_HERE'))()

Initializing the Library

	Lumina:Init()

Creating a Window

	local Window = Lumina:MakeWindow({
	    Name = "Lumina Example",
	    HidePremium = false,
	    SaveConfig = true,
	    ConfigFolder = "LuminaConfig",
	    IntroEnabled = true,
	    IntroText = "Welcome to Lumina",
	    IntroIcon = "rbxassetid://10723424505",
	    Icon = "rbxassetid://10723424505",
	    CloseCallback = function()
	        print("Window closed")
	    end
	})

Creating a Tab

	local Tab = Window:MakeTab({
	    Name = "Main Tab",
	    Icon = "rbxassetid://10734983707",
	    PremiumOnly = false
	})

Creating a Section

	local Section = Tab:AddSection({
	    Name = "Settings Section"
	})

Creating a Button

	Tab:AddButton({
	    Name = "Click Me",
	    Callback = function()
	        print("Button clicked")
	    end
	})

Creating a Toggle

	local Toggle = Tab:AddToggle({
	    Name = "Toggle Feature",
	    Default = false,
	    Flag = "toggleFeature",
	    Save = true,
	    Callback = function(Value)
	        print("Toggle set to:", Value)
	    end
	})
	
	-- Set toggle value programmatically
	Toggle:Set(true)

Creating a Slider

	local Slider = Tab:AddSlider({
	    Name = "Walkspeed",
	    Min = 16,
	    Max = 100,
	    Default = 16,
	    Increment = 1,
	    ValueName = "studs/s",
	    Flag = "walkspeedValue",
	    Save = true,
	    Callback = function(Value)
	        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
	    end
	})
	
	-- Set slider value programmatically
	Slider:Set(50)

Creating Notifications

	Lumina:Notify({
	    Title = "Success!",
	    Content = "Your operation was completed successfully.",
	    Icon = "rbxassetid://10723424505",
	    Duration = 5,
	    Theme = "Success", -- Options: Default, Success, Warning, Error
	    Callback = function()
	        print("Notification closed")
	    end
	})
