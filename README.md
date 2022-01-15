![Untitled](https://user-images.githubusercontent.com/96776358/149602887-f75608d9-0e50-4a7d-8f58-c73f4efe69e5.png)

# Documentation

All of the things you need to know to use SolMod is here

__Anything that says to create a file of a "Module Script" and to be named "Main Module" Is Required. Without doing so, it will not work OR said to create a "Main Module" means to make a "Module Script" and name it "Main Module"__

# Create SolMod Commands

{

"Wait, why do I have to use SolMod Modified commands? or anything else"	

Its because of Roblox saying that you cant import models if you dont own it or if its not by roblox

}

__SolMod Commands:__ Converting your **Solar Commands** to **SolMod Modified Commands**

This is the most simplest thing to do, all you need to do is to rename all of the Solar Commands to **Main Module** (Make sure to upload them to roblox). Then paste in this peice of code

(It will rename itself when its imported EX: if it was named "Test" in the code, it would rename the file to "test.command")

```lua
function command.MoveFile(location) script.Parent = location end
```

Example: ![image](https://user-images.githubusercontent.com/96776358/149603555-e381e8ef-99e7-42fc-bb1a-9b39a5e91a27.png)

This is all you have to do!

# Create SolMod Command Packs

You will need to create a new **ModuleScript** and name it **Main Module**, and write this code in: 

```lua
local Data = {
	["Name"] = "";
	["Description"] = "";
	
	["Version"] = "0.0.0";
}

function Data:MoveItemsInside(Location)
	for _, obj in pairs(script:GetChildren()) do obj.Parent = Location end
end

return Data
```

Then you can put in your **solar/solmod** commands inside of it _(Doesn't Matter)_

It should look like this: 

![image](https://user-images.githubusercontent.com/96776358/149603777-fa66bc96-5590-4cd6-a37a-951df015e8c6.png)

(Doesn't need to be in a folder)

Then make sure to upload the Main Main Module

# Creating SolMod Plugins

__Plugin system for solar is inactive. When its working soon, I'll fix the docs__

# Creating SolMod Themes

This is going to be just like creating a SolMod CommandPack

first you need to create another **MainModule** and write the code shown below

```lua
 local Data = {
	["Name"] = "";
}

function Data:MoveItemsInside(Location)
	for _, obj in pairs(script:GetChildren()) do obj.Parent = Location end
end
return Data
```

This is what it should look like

![image](https://user-images.githubusercontent.com/96776358/149604289-23ff267a-7c3a-4587-a37e-bbeed9caf21f.png)

You will see that its almost the same code as creating SolMod Command Packs, it just you need the name of the theme

Then put in your theme module script inside of the Main Module

Thats its, you just need to upload it and now you created a SolMod Theme

# Questions

Q: Why is the functions are like MoveITemsInside or MoveFile?

A: Its just so I can move the file to the correct location
