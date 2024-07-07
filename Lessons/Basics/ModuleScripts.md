# Module Scripts
Module scripts are scripts that will return data for normal scripts to use. They can have literally anything in them, including functions.

```lua
local Module = {}

Module.Hi = "Hello"

return Module
```

To access a module script you need to use `require` on them.

```lua
local RequiredModule = require(ModulePathHere)
print(RequiredModule) -- assuming its the one in the code block above

--[[
  OUTPUT:
  {
    Hi = "Hello"
  }
]]

-- You can also edit whatever is inside of the module
```
