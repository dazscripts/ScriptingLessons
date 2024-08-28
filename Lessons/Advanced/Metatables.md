# Metatables

## Creating Metatables
To Create a Metatable you should use `setmetatable`. 

```luau
--> setmetatable(table: {}, metatable: {})
local metatable = {
  __index = {},
}
setmetatable({}, metatable)
```
### Metamethods

Metamethods are certain things inside of your metatable that will cause it to do a certain action when something happens to it,
List of metamethods: [here](https://create.roblox.com/docs/luau/metatables#metamethods)
<br>

__For the sake of my sanity ill only cover the most useful metamethods.__

- `__index`<br>
Returns a value whenever you index a nil value inside of your table
> __index was fired when Value was indexed in the table and not found. Lua then searched through the __index table for an index called Value, and, finding one, returned that.
> (quote from documentation)

```lua
local index = {
  Value = "string"
}

local self = setmetatable({}, {__index = index})
print(self.Value) -- recieved "string" because there was nothing called "Value" inside the table
```

## Creating Classes
