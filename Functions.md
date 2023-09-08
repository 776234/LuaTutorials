# Functions in Lua
In Lua, functions serve as a powerful tool for encapsulating reusable code, enhancing performance, and improving code readability.

## Defining a Function
Functions in Lua can be defined as both global and local, similar to [variables](https://github.com/776234/LuaTutorials/blob/fdb992773b3b9279fae7df509ff5cf0a3c64cb57/Variables.md). To define a function, you can use the following syntax:

```lua
-- Create a function named `myFunction`
function myFunction()
    -- Function code here
end
```
Note: It's considered good practice to use the local keyword in front of a function definition when appropriate.

## Using a Function
Now that you have a grasp of how to define a function, let's explore how to use them effectively:

### Basic Function Usage
```lua
-- Define a function named 'myFunction'
local function myFunction()
    print("Hello, World!")
end

-- Call the function
myFunction() -- Output: "Hello, World!"
```
Here, we start with a basic example of defining and calling a function. This fundamental usage allows you to encapsulate and execute specific code whenever needed.

### Passing Arguments
You can enhance the functionality of functions by passing arguments:
```lua
local currentMoney = 100

-- Define a function 'giveMoney' that accepts 'amount' as an argument
local function giveMoney(amount)
    currentMoney = currentMoney + amount
end

-- Increase the 'currentMoney' variable by 500
giveMoney(500)

-- The 'currentMoney' variable now holds a value of 600
```
This demonstrates how functions can accept arguments, enabling you to customize their behavior based on input values.

### Returning Values
Functions can also return values, allowing you to retrieve and utilize the results:
```lua
-- Defining a function 'divideInHalf' that accepts 'num' as an argument
local function divideInHalf(num)
    return num / 2
end

-- Calling the function and printing the result
print(divideInHalf(10)) -- Output: "5"
```
In this example, we define a function that returns a value, providing you with a way to obtain and process data within your code.

Here's a more advanced example illustrating function returning:
```lua
-- Defining a function 'isNumberEven'
local function isNumberEven(num)
    -- '%' is an operator you will learn about later; it's used here to check if 'num' is even or not
    return (num % 2) < 1
end

-- Calling the function and storing the return in a local variable
local result = isNumberEven(3)

-- Printing the result
print(result) -- Output: "false"

-- Reassigning the variable with the new stored value
result = isNumberEven(2)

-- Printing the updated result
print(result) -- Output: "true"
```
This advanced example showcases how functions can return values for condition evaluation and data retrieval.

### Multiple Returns
Now, let's explore the concept of multiple returns:
```lua
-- Define a function called 'getProfile'
local function getProfile()
    local name = "John"
    local age = 25

    -- Using commas (',') allows you to return multiple values; remember the order.
    return name, age
end

-- Create variables to unpack the values returned by 'getProfile'. It's crucial to match the order of the returned values.
local name, age = getProfile()

-- Display the results
print("Name: " .. name .. ", Age: " .. age) -- Output: "Name: John, Age: 25"
```
In this code, we define the getProfile function, which returns both the name and age variables. By using commas when returning values, you can capture multiple return values. Remember to preserve the order of the returned values when unpacking them into variables.

### VarArgs
VarArgs, short for Variable Arguments, is a powerful feature in Lua that allows you to work with a variable number of function arguments. This can be especially useful when you want your functions to be flexible and adaptable to different situations.

To declare a function with VarArgs, you use the `...` notation as a parameter in the function definition. Here's an example:
```lua
-- Define a function 'printNames' that accepts a variable number of names as arguments
local function printNames(...)
    local names = {...} -- Unpack the VarArgs into a table

    -- Loop through the 'names' table and print each name
    for _, name in ipairs(names) do
        print("Hello, " .. name .. "!")
    end
end

-- Call the 'printNames' function with different numbers of arguments
printNames("Alice", "Bob", "Charlie") -- Output: "Hello, Alice!", "Hello, Bob!", "Hello, Charlie!"
printNames("Eve") -- Output: "Hello, Eve!"
printNames() -- No output because no arguments are provided
```

## Summary
With functions, you can modularize your code, making it easier to maintain and reuse, and enabling you to create more versatile and efficient Lua programs.
