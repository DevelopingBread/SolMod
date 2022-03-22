![Untitled](https://user-images.githubusercontent.com/96776358/149602887-f75608d9-0e50-4a7d-8f58-c73f4efe69e5.png)

Thank you for using SolMod

This took me forever to find a way to make this easier to install solar or commands. (idk why dont ask me or I'll beat you up)

```diff
Update 1.3:
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

--// Ui
CustomUi <bool> -- Uses a custom ui that you or someone else made for solar. Ui location is in Assets.SolMod.UI
CustomTheme <bool> -- Uses a custom theme that you or someone else made for solar. Theme location is in Assets.SolMod.UI

--// AlphaFeatures
UseBugFixedSolar <bool> -- Uses a bugfixed solar that star never fixed yet. (None are there yet. You also need to change UseSolarVersion to a type of bugfixed one. Listed in docs)
UseSolarCommands <bool> -- Uses regular solar commands. Add them in Assets.SolMod.SolarCommands

--// Developer
Debug <bool> -- Used for debugging if theres a problem with installing SolMod
```
## Documentation
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

On that line or somewhere, pase in this code:
```lua
function CommandObject:SetSolModData(Data: {})
	setmetatable(Data, {__index = function(table, index) error("No index", index) end})

	Data.Script.Parent = Configuration:WaitForChild("Commands")
	Data.Script.Name = Data.Name .. ".command"

	self.Name = Data.Name
	self.Description = Data.Description
	self.PermissionLevel = Data.PermissionLevel

	return self
end
```
And thats it! You are now SolMod Compatible

## SolMod Commands
**This is for you when you need to convert your solar commands too SolMod ones**

This is one of the most easist things to do

In your solar command, around line 3 there should be something like *local Command = API:CreateCommand()*

You want to paste in this code at the top and you can delete *SetName* , *SetDescription* , *SetPermissionLevel*
```lua
:SetSolModData({
	Script = script; -- DO NOT CHANGE THIS. if you do i will be sad ;(
	
	Name = "solmodtest";
	Description = "Time to check if loading in modules worked!";
	PermissionLevel = 4;
})
```

It should look like this

![image](https://user-images.githubusercontent.com/96776358/159592175-4ea47c00-29aa-41c5-a298-2ae629a1e2dd.png)

Then you must name the module *MainModule* and upload it. After that you can share the Id to anyone else who wants to use it (Make sure to enable *Distribute on Marketplace*)

![image](https://user-images.githubusercontent.com/96776358/159592348-a43f3db7-129b-4587-a7f2-8b39ba17dd7a.png)
