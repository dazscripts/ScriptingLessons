# If Statements
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
