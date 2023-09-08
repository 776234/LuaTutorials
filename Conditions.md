# Conditions in Lua
Conditional statements in Lua are a fundamental tool for controlling the flow of your code. They enable you to make decisions and execute specific blocks of code based on certain conditions.

## The `if` Statement
The `if` statement is the most basic form of conditional statement. It allows you to execute a block of code if a specified condition is true. Here's a simple example:
```lua
local temperature = 25
if temperature > 30 then
    print("It's hot outside!")
end
```
In this example, the code inside the if block will only execute if the temperature is greater than 30.

## The `else` Statement
You can enhance your conditional logic by using the `else` statement. It provides an alternative block of code to execute when the initial condition is false. Here's an example:
```lua
local age = 17
if age >= 18 then
    print("You are an adult.")
else
    print("You are a minor.")
end
```
In this case, the code inside the `if` block runs if age is 18 or older, and the code inside the `else` block runs if age is less than 18.

## The `elseif` Statement
For more complex conditions, you can use the `elseif` statement to check additional conditions after the initial if statement. Here's an example:
```lua
local score = 75
if score >= 90 then
    print("A")
elseif score >= 80 then
    print("B")
elseif score >= 70 then
    print("C")
else
    print("F")
end
```
In this example, Lua checks the score against multiple conditions and prints the corresponding grade.

# Loops in Lua: Conditional Loops and Iterative Loops
Loops in Lua are essential for executing a block of code repeatedly. They provide the necessary control flow to handle various tasks efficiently. Lua offers two primary types of loops: conditional loops and iterative loops. In this tutorial, we'll explore both types to help you understand how to use them effectively in your Lua programs.

## Conditional Loops: The while Loop
A conditional loop, commonly known as the `while` loop, repeatedly executes a block of code as long as a specified condition remains true. Here's the basic structure of a while loop:
```lua
while condition do
    -- Code to execute repeatedly
    task.wait()
end
```
The loop continues to execute as long as the condition remains true. Once the condition becomes false, the loop terminates, and the program proceeds to the next statement.

Here's an example of a `while` loop that counts from 1 to 5:
```lua
local count = 1
while count <= 5 do
    -- Add 1 to the count variable
    count = count + 1

    -- Wait 1 second before looping again
    task.wait(1)
end
```
In this example, the loop runs until count is no longer less than or equal to 5.

If you would like to stop the execution of a `while` loop forcefully, you may do so using the `break` keyword. Here's how to do that:
```lua
local count = 0

-- Putting 'true' here will make this an infinite loop
while true do
    if count == 10 then
        -- If the 'count' variable equals 10 then let's stop the loop with the 'break' keyword
        break;
    end

    -- Add 1 to the count variable
    count = count + 1

    -- Wait 1 second before looping again
    task.wait(1)
end
```

***Note: you MUST include `task.wait()` somewhere in your `while` loop to prevent crashing***

## Conditional Loops: The repeat-until Loop
The repeat-until loop is another form of a conditional loop that executes a block of code at least once and then repeats as long as a specified condition remains false. Its structure looks like this:
```lua
repeat
    -- Code to execute repeatedly
until condition
```
Unlike the while loop, the repeat-until loop ensures that the code block runs at least once before checking the condition. It continues executing the code block until the condition becomes true.

Here's an example that illustrates the repeat-until loop:
```lua
local count = 1
repeat
    -- Add 1 to the count variable
    count = count + 1

    -- Wait 1 second before looping again
    task.wait(1)
until count > 5
```
In this example, the code block runs once, and then the loop continues until count is greater than 5.

If you would like to stop the execution of a `repeat` loop forcefully, you may do so using the `break` keyword. Here's how to do that:
```lua
local count = 0

-- Putting 'true' here will make this an infinite loop
repeat
    if count == 10 then
        -- If the 'count' variable equals 10 then let's stop the loop with the 'break' keyword
        break;
    end

    -- Add 1 to the count variable
    count = count + 1

    -- Wait 1 second before looping again
    task.wait(1)
until
```

***Note: you MUST include `task.wait()` somewhere in your `repeat` loop to prevent crashing***

## Iterative Loops: The for Loop
Iterative loops, also known as for loops, are designed for iterating over a sequence of values, such as a range of numbers or elements in a table. The basic structure of a for loop is as follows:

```lua
for variable = start, stop, step do
    -- Code to execute for each iteration
end
```
The for loop initializes the variable with the start value and increments it by step until it reaches the stop value. It's particularly useful when you know the number of iterations in advance.

Here's an example of a for loop that prints numbers from 1 to 5:
```lua
for i = 1, 5 do
    print(i)
end
```
This loop starts at 1, increments by 1 by default, and stops when i reaches 5.

## Iterative Loops: The for Loop with Step
You can also specify a custom step value in a for loop. For example, to print even numbers between 2 and 10, you can use the following code:

```lua
for i = 2, 10, 2 do
    print(i)
end
```
In this loop, the i variable starts at 2 and increments by 2 until it reaches 10.

## Iterative Loops: Using `pairs`, `ipairs` and `next`
In Lua, you can iterate over tables using the for loop with the `pairs` and `ipairs` functions and the `next` construct. These functions provide different ways to iterate over table elements.
*Note: `next` is way more performant in Luau.*

### Using `pairs`
The `pairs` function allows you to iterate over all elements in a table, including both keys and values. Here's the syntax:
```lua
for key, value in pairs(table) do
    -- Code to execute for each key-value pair
end
```

Here's an example:
```lua
local fruits = {apple = "red", banana = "yellow", grape = "purple"}

for key, value in pairs(fruits) do
    print(key .. " is " .. value)
end
```
This code iterates over the fruits table, printing the key-value pairs.

### Using `ipairs`
The `ipairs` function is specifically designed for iterating over arrays or lists where keys are sequential integers starting from 1. Here's the syntax:
```lua
for index, value in ipairs(array) do
    -- Code to execute for each element in the array
end
```

Here's an example:
```lua
local numbers = {10, 20, 30, 40, 50}
for index, value in ipairs(numbers) do
    print("Element at index " .. index .. " is " .. value)
end
```

### Using `next`
The `next` construct functions similarly to the `pairs` function, enabling you to iterate through all elements within a table, encompassing both keys and values. The syntax is as follows:
```lua
for index, value in next(table) do
    -- Code to execute for each key-value pair
end
```

Here's an example:
```lua
local array = {10, 20, "orange", "blue", true, false}
for index, value in next, array do
    print("Element at index " .. index .. " is " .. value)
end
```

This code iterates over the numbers array, printing the index and value of each element.
## Summary
Conditional statements are essential for creating flexible and responsive code, enabling your programs to adapt to various situations and inputs.
