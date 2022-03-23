![Untitled](https://user-images.githubusercontent.com/96776358/149602887-f75608d9-0e50-4a7d-8f58-c73f4efe69e5.png)

Thank you for using SolMod

This took me forever to find a way to make this easier to install solar or commands. (idk why dont ask me or I'll beat you up)

**I forgot to replace the Cmdr theme for SolMod so ig it comes with it 💀**

Dont click on this link: https://cdn.discordapp.com/attachments/820536497522212906/840797846999138324/video0.mp4

```diff
Update 1.3.2:
+ Added plugins
+ Added a end warn "SolMod has loaded [ x | Plugin(s)] [ x | Command(s)]"

Update 1.3.1:
+ Made it so you can change any of the functions from Name to Metadata (Look in docs if you dont understand :/)
+ I give back the pie I owe you 🥧

Update 1.3.0:
+ Cleaned up the code
+ Made things more compact
+ Made life more easier to change commands to solmod type
+ Re-Done the whole docs
+ I feel happy making this :)
- I removed pie, sorry :(
```

## Settings
```lua
--// Solar
AutoUpdateSolar <bool> -- Automatically updates solar to the latest version.
UseSolarFolder <bool> -- Uses a manual instalation of solar (You're gonna need to read the docs, TRUST ME)
UseSolarVersion <string> -- Uses a installation that is included (In docs)
RegisterCommands <bool> -- Registers commands for solar
Commands <table {int}> -- Add in your solmod commands here (ID FORM)
Plugins <table {int}> -- Add in your solmod plugins here (ID FORM)

--// Ui
CustomUi <bool> -- Uses a custom ui that you or someone else made for solar. Ui location is in Assets.SolMod.UI
CustomTheme <bool> -- Uses a custom theme that you or someone else made for solar. Theme location is in Assets.SolMod.UI

--// AlphaFeatures
UseBugFixedSolar <bool> -- Uses a bugfixed solar that star never fixed yet. (None are there yet. You also need to change UseSolarVersion to a type of bugfixed one. Listed in docs)
UseSolarCommands <bool> -- Uses regular solar commands. Add them in Assets.SolMod.SolarCommands

--// Developer
Debug <bool> -- Used for debugging if theres a problem with installing SolMod
```
# Documentation
## Working Versions
```diff
+ 0.3.4-Pre

! 0.3.3-Pre

- 0.3.2-Pre

- 0.12-Beta

- 0.11-Beta
```
## Included Versions
```lua
Solar Versions Included {
	"0.3.4-Pre"
}

Solar Bugfixed Versions Included {
	"None at the moment"
}
```

## API
**This is FOR YOU if you are installing a manual installation of solar**

This is a very easy process to do. Inside your installation of solar, scroll down until you find Command Functions
![image](https://user-images.githubusercontent.com/96776358/159591281-cd7f9d42-030c-4576-8284-03c46df33ceb.png)

This isn't strict where you place it but I recomend you put it above every other function and under the ReturnObject table
![image](https://user-images.githubusercontent.com/96776358/159591432-d49760a6-002e-40aa-9a37-953cf3b3b3bd.png)

On that line or somewhere, paste in this code:
```lua
function CommandObject:SetSolModData(Data: {})
	Data.Script.Parent = Configuration:WaitForChild("Commands")
	Data.Script.Name = Data.Name .. ".command"

	self.Name = Data.Name
	self.Description = Data.Description
	self.PermissionLevel = Data.PermissionLevel
	for _, Argument in pairs(Data.Arguments) do
		table.insert(self.Arguments,{
			Name = Argument[1],
			Type = Argument[2],
			Required = Argument[3],
			Options = Argument[4] or {}
		})
	end
	self.Options = Data.Options
	self.Metadata = Data.Metadata
	
	return self
end
```
And thats it! You are now SolMod Compatible

## SolMod Commands
**This is for you when you need to convert your solar commands too SolMod ones**

This is one of the most easist things to do

In your solar command, around line 3 there should be something like *local Command = API:CreateCommand()*

You want to paste in this code at the top and you can delete *every other function*
```lua
-- Use solar's docs to understand how this works
:SetSolModData({
	Script = script; -- This is very important for the api to change the properties of the script
	
	Name = "solmodtest";
	Description = "Time to check if loading in modules worked!";
	PermissionLevel = 4;
	Arguments = {
		{"arg1", "string", true};
		{"arg1", "player", false};
	};
	Options = {
		ParseArguments = true,
		HideExecutionOnClient = false,
		YieldOnClient = false,
	};
	Metadata = {
		LastCompatibleVersion = "0.3.4",
		ForceCompatibility = false,
	}
})
```

Then you must name the module *MainModule* and upload it. After that you can share the Id to anyone else who wants to use it (Make sure to enable *Distribute on Marketplace*)

![image](https://user-images.githubusercontent.com/96776358/159768432-1da5cfb1-d14d-4929-b998-bd34e07dfbc2.png)

## Plugins

For plugins, they are different and doesn't need the api to be modified.

You would only add some code to the table on the modulescript

```lua
	SolModData = {
		Script = script; -- No touch
		
		Name = "example"; -- Name of the plugin, like the NAME OF IT which would convert it into that: example.plugin
		Description = "example plugin lol"; -- description
		Version = "0.0.0"; -- version of the plugin
	};
```

should be like this:

```lua
local Plugin = {
	SolModData = {
		Script = script;
		
		Name = "example";
		Description = "example plugin lol";
		Version = "0.0.0";
	};
	
	Name = "Example Plugin",
	Type = "client", --// 'client' will run the plugin on the client-side and 'server' will run the plugin on the server-side
}

function Plugin.start()
	print("Hello! I'm a plugin :)")
end

return Plugin
```

Then make sure to name it MainModule and upload it to roblox ENABLE **Distrubute on Marketplace** ![image](https://user-images.githubusercontent.com/96776358/159768383-4b93172b-2db8-4199-8a24-317b52f8589b.png)

## Gui

When changing the gui to your liking, you need to know *LuaU* and *Gui* 

The template gui is in Assets.SolMod.UI

Make sure to edit the localscript in the gui to work with it.

# Themes

## CmdR

[CmdR Gui Theme.zip](https://github.com/DevelopingBread/SolMod/files/8335043/CmdR.Gui.Theme.zip)

![image](https://user-images.githubusercontent.com/96776358/159754382-da54412c-4e60-4431-a6ad-8b7f92fb904b.png)
