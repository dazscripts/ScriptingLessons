# Variables

## About Variables

### What is a Variable? 

A variable is an object in your code designed to be used as storage to reference to other values and objects efficiently.

### What are some use cases for this?

A use case would be for setting a number in your script, for example if you want to store the number "10" you can make a variable for it and anything that needs that number can just use that variable instead, this is useful because if you for some reason need to change that 10 to an 11 you only need to change the 10 once instead of every single bit of code that will use that 10.

<details>
<summary>Correct and Incorrect Examples</summary>

please note i dont expect you to understand any of the code in here, its just an example

**Correct**
```lua
-- Code Purpose:
-- Add 1 to CurrentNumber variable until CurrentNumber is not less than ComparedNumber

local CurrentNumber = 0
local ComparedNumber = 10
-- code below can use this variable, code above variable cant use it

while ComparedNumber < CurrentNumber do
    CurrentNumber += 1 -- this is the same as doing CurrentNumber = CurrentNumber + 1
    print(CurrentNumber, ComparedNumber)
    task.wait(0.5)
end
```

**Incorrect**
```lua
-- this code will not use any variables for the logic which will
-- make it a lot harder to read and make it look messy

-- Code Purpose:
-- Loop through table and pring all the values until Index is
-- Greater than 10

local TestTable = {
1,2,3,4,5,6,7,8,9,10,11,12,13
}

for Index, Value in TestTable do
    print(Index)
    if Index > 10 then return end -- exits the loop if index is above 10
end
```
</details>


## How to use variables

### Creating Variables

You can create a variable by typing `local` in all lowercase with whatever you want the variable to be named coming after it.
To set a value to the variable you can put = and then whatever you want the variables value to be, you can set it to a string, number, boolean(true/false) or even another variable

**Example:**
```lua
local BlankVariable -- this is just the same as nil
local NumberVariable = 10
local StringVariable = "Hello"
local BoolVariable = true
local VariableReference = NumberVariable
```
