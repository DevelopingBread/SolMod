![Untitled](https://user-images.githubusercontent.com/96776358/149602887-f75608d9-0e50-4a7d-8f58-c73f4efe69e5.png)

# Documentation

All of the things you need to know to use SolMod is here

__Anything that says to create a file of a "Module Script" and to be named "MainModule" Is Required. Without doing so, it will not work OR said to create a "MainModule" means to make a "Module Script" and name it "MainModule"__

# Create SolMod Commands

{

"Wait, why do I have to use SolMod Modified commands? or anything else"	

Its because of Roblox saying that you cant import models if you dont own it or if its not by roblox

}

__SolMod Commands:__ Converting your **Solar Commands** to **SolMod Modified Commands**

This is the most simplest thing to do, all you need to do is to rename all of the Solar Commands to **MainModule** (Make sure to upload them to roblox). Then put in this peice of code down there

```lua
function command:MoveFile(location) script.Parent = location; script.Name = string.lower(table.concat(string.split(command["Name"], "")) .. ".command") end
```

(It will rename itself when its imported EX: if you change SolModName to "Test" in the code, it would rename the file to "test.command", this is how you would run the command)

![image](https://user-images.githubusercontent.com/96776358/149606697-a4872fb0-fb02-441d-bd61-68adf248c7da.png)

This is all you have to do!

# Create SolMod Command Packs

You will need to create a new **ModuleScript** and name it **MainModule**, and write this code in: 

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

__Plugin system for solar is inactive. When its working soon, I'll fix the docs__

# Creating SolMod Themes

This is going to be just like creating a SolMod CommandPack

first you need to create another **MainModule** and write the code shown below

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

![image](https://user-images.githubusercontent.com/96776358/149604289-23ff267a-7c3a-4587-a37e-bbeed9caf21f.png)

You will see that its almost the same code as creating SolMod Command Packs, it just you need the name of the theme

Then put in your theme module script inside of the MainModule

Thats its, you just need to upload it and now you created a SolMod Theme

# Questions

Q: Why is the functions named MoveFile?

A: Its just so I can move the file to the correct location
