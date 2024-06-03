# PreKnowledge
This is anything you will need to know PRIOR to writing or learning how to write any code.

## Data Types

**What is a DataType?**
A DataType is a chunk of data that you can use inside of your scripts. <br>
Luau has 4 DataTypes however i am only gonna cover 3 of them for now. there is `Number`, `String`, `Boolean`, and `Table`. 

### Numbers
This is pretty self explanatory, its just a number

### Strings
A strung is a chunk of text you can wrap in quotation marks, if you dont wrap it in quotation marks you will get an error

```lua
-- Correct
'Hello! this is a String'
"Hello! this is a String"
'Hello! i can use "Quotation Marks" inside of a string like this'

-- Incorrect
Hello! this is a string
```

**Combining Strings**
There are two ways to combine strings, `string` .. `string/variable` or ``` `string {Variable}` ```

```lua
-- Variables
local NumberVar = 4
local SentenceVar = "I wanna buy "

-- Normal way of combining strings
local CompletedStringNormal = [SentenceVar] .. NumberVar .. " ducks!"
print(CompletedStringNormal)

-- Fancy way of combining strings
local CompletedStringFancy = `{SentenceVar}{NumberVar} ducks!`
print(CompletedStringFancy)
```

### Booleans
Booleans are a DataType that represent yes and no, for example you can check if something is true and run an action based on that.

`true`, `false`

## Expressions
An expression is a pair of 2 symbols that will check two values and return a boolean as a result. you can use these on any DataType <br>

```lua
-- This code uses if statements which havent been documented in the lessons yet

if 1 == 1 then
-- this code will run because 1 is equal to 1
end

if 1 ~= 1 then
  -- this code would not run since "is 1 not equal to 1" would return as false 
  -- which tells the script to not run this section of code
end
```

| Symbols | Explanation |
| ------- | ----------- |
| == | Is equal to |
| ~= | Does not equal |
| >= | Greater than or equals |
| <= | Less than or equals |

