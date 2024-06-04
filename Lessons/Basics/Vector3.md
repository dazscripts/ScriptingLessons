# Vector3
A Vector3 represents 3 numbers that are used to determine an objects position in a 3d space. it uses 3 numbers: XYZ. They are used to determine the position of things like a part.

## Creating a Vector3
Vector3 can be created using `Vector3.new()`, it takes 3 number arguements.
```lua
Vector3.new(1,2,3)
```

## Vector3 Properties
When you think of a vector3's properties you can imagine them like a table
```
Vector3.new(1,2,3) -> {
    X = 1,
    Y = 2,
    Z = 3
}
```
You can read these properties just like you can with a table, it however is not a table so you cant do things like for loops to them.
```lua
local Vector = Vector3.new(1,2,3)
print(Vector.X)
```
