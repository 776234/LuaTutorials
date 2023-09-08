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

## Summary
Conditional statements are essential for creating flexible and responsive code, enabling your programs to adapt to various situations and inputs.
