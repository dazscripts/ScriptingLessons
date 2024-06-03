# Tables
Tables are EXTREMELY useful, you can store a ton of data inside of them and use them for basically anything

Tables are pretty tricky to understand however so i will try to demonstrate it with a literal github table

## Creating a Table
To create a table you can use the curly braces: {} this creates a new table with nothing in it. To define values into the table you can just put things into it separated by commas.

```lua
-- Blank Table
local NewTable = {}

-- Not Blank Table
local NewTable = {
    "String",
    10837,
    true,
    false
}
```

### What is an Index?
An index is the position of a value inside of a table, it can be manually defined when creating the table or when adding the value into the table. If an index is not provided then the index will just be one more than the length of the table (# +1).

```lua
-- Table with automatic indexes
local NewTable = {
    "String", true, false
}
print(NewTable)
--[[ 
    Output: {
        [1] = "String",
        [2] = true,
        [3] = false
    }
]]

-- Table with manual indexes

local NewTable = {
    [-1] = "String",
    ["StringIndex"] = true,
}
-- NOTE: i dont recommend having tables with multiple DataTypes as indexes. this is just an example.

print(NewTable)
--[[
    Output: {
        [-1] = "String",
        ["StringIndex"] = true
    }
]]

-- This will also work for string indexes
local NewTable = {
    Value1 = "hi",
    Value2 = 123
}
```

### What is a Value?
A value is just whatever is given to the table that you want to store.

## Working with a Table
When working with a table you will treat them the same way as an instance property where you can use the `dot notation` to access and change their values.

to access a specific value you will access the table and type whatever index is assigned to that value

```lua
local StringVar = "Value2"
local NewTable = {
    Value1 = "hi",
    Value2 = {
        1, 2, 3
    }
}

-- If i want to read Value2 i can do it like this
print(NewTable.Value2)
print(NewTable[StringVar]) -- same thing as above but with a variable

-- I can Change Value2 like this
NewTable.Value2 = "Hello i am not a table anymore"
print(NewTable.Value2) -- Output: Hello i am not a table anymore

-- To create a new value i can do this
NewTable.ThisIsACustomIndex = "Hi"

-- this will do a automatic index
-- i will do a tutorial on the table global soon
table.insert(NewTable, "Hi")
```