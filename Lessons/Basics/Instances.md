# Instances

## What are Instances?
An instance is an object inside the game that will show up inside the roblox studio explorer. they have specific purposes and can be created by scripts.

## Path Constructors
Instances can be accessed through something called a path, you can create a path using a dot notation (.) for all the instances until you find the instance you need

```lua
-- Find a part in the workspace
-- workspace can be accessed by just typing workspace

workspace.Part
game.Workspace.Part -- game.Workspace is unnecesary but will still work
```

## Creating Instances
Instances can be created with the function `Instance.new()` and providing a string parameter, this will create a new instance with its own properties and methods. If you do not set the parent of a created instance then it will be parented to nil. 
```lua
local Part = Instance.new("Part")
```
### Properties
Properties are special values on an instance that tell instance how to act, for example changing the position on a part will make the part move and setting the parent will change the path of the instance.

```lua
local Part = Instance.new("Part")

Part.Parent = workspace
Part.Anchored = true
```

### Methods
A method is a function that will directly run an action from an instance

```lua
local Part = Instance.new("Part")
local Part2 = Instance.new("Part")

Part.Parent = workspace
Part2.Parent = Part

local MethodTest = Part:FindFirstChild("Part") -- Returns Part2
local MethodTest2 = Part2:FindFirstChild("Part") -- Returns nil

local Children = Part:GetChildren() -- Returns a table with Part2 in it

task.wait(3)

Part:Destroy() -- Destroys instance and all its descendants
```
