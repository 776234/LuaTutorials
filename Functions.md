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
```lua
-- Define a function named 'myFunction'
local function myFunction()
    print("Hello, World!")
end

-- Call the function
myFunction() -- Output: "Hello, World!"
```

You can also pass arguments to a function, enabling you to customize its behavior. Here's a more advanced example of how functions can be utilized:
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

Functions can also return values using the `return` keyword. Consider this example:
```lua
-- Defining a function 'divideInHalf' that accepts 'num' as an argument
local function divideInHalf(num)
    return num / 2
end

-- Calling the function and printing the result
print(divideInHalf(10)) -- Output: "5"
```

Here's a more advanced example of function returning:
```lua
-- Defining a function 'isNumberEven'
local function isNumberEven(num)
    -- '%' is an operator you will learn about later, it's just used for this example.
    return num % 2 == 0
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
Functions that return values are particularly useful for evaluating conditions and retrieving data.

## Summary
With functions, you can modularize your code, making it easier to maintain and reuse, and enabling you to create more versatile and efficient Lua programs.
