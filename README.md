![Untitled](https://user-images.githubusercontent.com/96776358/149602887-f75608d9-0e50-4a7d-8f58-c73f4efe69e5.png)

Thank you for using SolMod

There are already 3 ids are in ```SolMod/FTBR/ConfigReplace``` by **defualt**

Right at this moment, there isn't any modified commands for letting commands be used in SolMod, But follow the Documentation, and it will guide you on how to do it

Any bugs that is found, please report it to me, or if you have any problems, then ping/dm me in Solar server [Expired Bread#8976] (684808662157361170)

For the commands to work, make sure to check in ```SolMod/FTBR/Settings```

### **Reminder: Put the SolMod folder in ServerScriptService**

# Documentation

All of the things you need to know to use SolMod is here

```Anything that says to create a file of a "Module Script" and to be named "MainModule" Is Required. Without doing so, it will not work OR said to create a "MainModule" means to make a "Module Script" and name it "MainModule"```

# Create SolMod Commands

> "Wait, why do I have to use SolMod Modified commands?"	

> 1. Its because of Roblox saying that you cant import models if you dont own it or if its not by roblox
> 2. The creator of the command/theme/command pack can easily update it and you don't have to scavenge for it
> 3. You can just put in the Id in ```SolMod/FTBR/ConfigReplace``` and automatically install the command, without the need of puting it in somewhere

### **SolMod Commands:** Converting your ```Solar Commands``` to ```SolMod Commands```

This is going to be just like creating Command Packs (Below here) but this only requires you to put in a single command inside and no needs to modify anything else

Create a ModuleScript and put the code like this:

```lua
local Data = {}

function Data:MoveFile(Location)
	local obj = script:FindFirstChildOfClass("ModuleScript")
	obj.Parent = Location
end

return Data
```
Should look like this

![image](https://user-images.githubusercontent.com/96776358/149608102-0c2ce520-b3f7-4cba-b803-c4528f425322.png)

Then insert your Solar Command inside (This is how it should look like)

![image](https://user-images.githubusercontent.com/96776358/149607965-e1e92207-25a8-4a5c-9223-187729ea5415.png)

# Create SolMod Command Packs

You will need to create a new ```ModuleScript``` and name it ```MainModule```, and write this code in: 

```lua
local Data = {
	["Name"] = ""; -- What pack is this?
	["Description"] = ""; -- What does it do?
	
	["Version"] = "0.0.0"; -- What Version is this on?
}

function Data:MoveFile(Location)
	for _, obj in pairs(script:GetChildren()) do 
		obj.Parent = Location
	end
end

return Data
```

Then you can put in your solar commands inside of it _(It must be regular solar commands NOT SolMod Commands)_

It should look like this: 

![image](https://user-images.githubusercontent.com/96776358/149603777-fa66bc96-5590-4cd6-a37a-951df015e8c6.png)

(Doesn't need to be in a folder)

Then make sure to upload the Main MainModule

# Creating SolMod Plugins

```Plugin system for solar is inactive. When its working soon, I'll fix the docs```

# Creating SolMod Themes

This is going to be just like creating a SolMod CommandPack

first you need to create another ```MainModule``` and write the code shown below

```lua
 local Data = {
	["Name"] = ""; -- What the name of this theme?
}

function Data:MoveFile(Location)
	for _, obj in pairs(script:GetChildren()) do obj.Parent = Location end
end
return Data
```

This is what it should look like

```Make sure the theme ModuleScript is named "defualt.theme", because Im lazy to make it work if its a different name lol```

![image](https://user-images.githubusercontent.com/96776358/149604289-23ff267a-7c3a-4587-a37e-bbeed9caf21f.png)

You will see that its almost the same code as creating SolMod Command Packs, it just you need the name of the theme

Then put in your theme module script inside of the MainModule

Thats its, you just need to upload it and now you created a SolMod Theme

# Questions

> Q: Why is the functions named MoveFile?
> A: Its just so I can move the file to the correct location

> Q: Why are there require code?
> A: Its to load in the commands for Solar

> Q: Can any of the codes be malicious?
> A: Yes, but only if the creator of the command has put in malicious code inside. Before adding any command to Solar, I would check if any of it is malicious. Or if you know they are trusted within the community, then its safe to assume its ok.
