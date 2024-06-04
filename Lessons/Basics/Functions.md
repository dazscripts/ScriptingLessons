# Functions
Functions are basically a chunk of code that you can have your scripts choose to run at any time, they can be given values that let the code inside of them behave differently.

## Creating Functions
To create a function you type `local function FunctionNameHere()` and then an `end` block

```lua
local function ThisIsAFunction()
    -- Code Goes here
end
```
After doing this you can write any code you want to run inside of this function you made.

You can also create a global function inside a script. this lets any code inside that script use the function even if its above where the function itself is.

```lua
-- local function, code above it cant access it
local function LocalFunction()
end

-- Global Function
function GlobalFunction()
end
```

## Running Functions
To run a function you have created you can type the functions name followed by parenthasis (i cant spell)

```lua
local function TestFunction()
    print("Function Ran")
end

TestFunction()
```

## Function Parameters
Function parameters are a value you can give to a function when calling it. to define the parameters a function will recieve you put the parameter names inside of the () when creating the function.

To provide these parameters to the function you just have values separated by commas in the order that the function will expect them.

```lua
local function ParameterTesting(Parameter1, Parameter2)
    print(Parameter1, Parameter2)
end

ParameterTesting("String", 123)
-- Output: String 123

ParameterTesting(true)
-- Output: true nil
```

If a parameter is not provided then it will be nil when the functions code runs.