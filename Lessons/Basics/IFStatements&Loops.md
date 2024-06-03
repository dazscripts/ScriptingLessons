# If Statements and Loops

## If Statements
**What is an "if statement"?**
an if statement lets you check if a certain condition is met to run code.

**Examples**

```lua
if true then
-- will run
end

if false then
-- will not run, behind the scenes think about an if statement like
-- a condition for if something is true, so it will only run if given
-- a trueish value
end

if false == false then
-- will run
end

if "hello" then
-- will run because "hello" is not nil, nil is a falseish value
-- in luau so if you put something in an if statement thats nil
-- then it wont run the code
end
```

## Loops
**What is a "Loop"?**
a loop is a segment of code that will run multiple times. There are 3 kinds of loops! for loops, while loops, and repeat until loops

### For Loops
A for loop can be used in a few different ways, it has a use for tables to run code on all the tables contents and it can also be used to run a chunk of code a specific number of times. **Loops arent the same as functions**

```lua
-- Table
-- NOTE: dw about this one till u learn tables
local NewTable = {"i am a string", "i am also a string"}
for Index, Value in NewTable do
print(Index, Value)
end


-- Repeating # of times
--[[
this version takes 3 arguements, starting number, ending number, interpolater
what this will do is that it will start with an Index
that is equivalent to the starting number and add the interpolater
to that number until it reaches or exceeds the ending number.
each time the Index is changed it will run any code inside the loop.

NOTE: the 3rd arguement isnt required
]]

for Index = 0, 10, 1 do
print(Index)
end
-- Output: 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
-- Any of the arguements can be negative, for example:

for Index = 10, 0, -1 do
print(Index)
end
-- Output: 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
```

## Repeat Until Loop
this will run a segment of code until a condition is not met, the condition is put after the "until" keyword, it acts the same as an if statement

```lua
local Number = 0
repeat
Number += 1 -- adds 1 to Number
print(Number)
until Number >= 5 -- Stops the loop when Number is greater than or equal to 5.
```


## While Loops
this is basically the same thing as a repeat until loop except if the condition is met again after the loop stops it will start the loop again (i think? i might be wrong abt this but i cant test it rn lol)

however one big difference is that unlike the repeat until loop this checks the condition BEFORE running the code inside the loop, whereas repeat until will check AFTER, so keep that in mind.

```lua
local number = 0
while number < 6 do
number += 1
print(number)
end
```
