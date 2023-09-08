# Variables in Lua
In Lua, variables serve as storage containers for data. They can hold values of any type, and you can think of them as references to specific values that you've assigned.

## Global Variables
Global variables in Lua can be accessed from any part of your code. You can define them like this:

```lua
variable = nil
```
*Note: Assigning `nil` to a variable means it has no value assigned to it.*

## Local Variables
Local variables in Lua are only accessible within the same scope of code or within lower-level scopes. To declare a local variable, you must use the local keyword in front of the variable name. Here's how you define a local variable:

```lua
local variable = nil
```

## Using Variables Effectively
Now that you have a solid understanding of how to create both global and local variables, let's delve into their effective usage:

When you need to store and manipulate data in your Lua code, you can do so as demonstrated in this example:
```lua
-- Storing and manipulating data using variables

-- Declare a local variable 'count' and initialize it with the value 0
local count = 0

-- Increment the 'count' variable by 1
count = count + 1

-- Display the current value of 'count' in the console
print("The current count is: " .. count)

-- Update 'count' with a new value, in this case, 10
count = 10

-- Display the updated value of 'count'
print("Now, the count is: " .. count)
```
In this code, we employ the print function to communicate our results to the console, providing clarity on how variables are employed to store and manipulate data.

However, if you encounter a scenario where you need to access data from a lower scope outside of it, global variables become essential:
```lua
-- Defining a global variable from within a nested scope
do
    -- Within this block, 'localScore' is a local variable
    local localScore = 42
    
    -- Assign the local 'localScore' to the global variable 'globalScore'
    globalScore = localScore
end

-- Accessing the global variable 'globalScore' from outside the scope
print("The global score is: " .. globalScore) -- Works as expected

-- Attempting to access 'localScore' from outside the scope will result in an error
```
*Note: The usage of `do...end` creates a nested scope, preventing localized variables like 'localScore' from being accessible to the outer scope.*

However, it's generally recommended to minimize the use of global variables. An alternative approach is to employ a local variable outside of the nested scope to store the data:
```lua
local score = nil

-- Defining a global variable from within a nested scope
do
    -- Within this block, 'localScore' is a local variable
    local localScore = 42

    -- Assign the local 'localScore' to the global variable 'globalScore'
    score = localScore
end

-- Works as expected since we transferred data to the local variable
print("The score is: "..score)

-- Attempting to access 'localScore' from outside the scope will result in an error, but you may access the value assigned to 'score'
```
By adopting this approach, you can maintain better control over your variables and reduce potential issues associated with global scope.

You can also create a "multi-variable," which allows you to assign values to multiple variables simultaneously:
```lua
-- Assign values to each variable
local one, two, three = 1, 2, 3

-- Print the result
print(one, two, three) -- Output: "1 2 3"
```
In this example, we've created a "multi-variable." These are especially useful for tasks like unpacking function arguments, making your code more concise and readable.

## Naming Conventions in Lua
Naming conventions in programming define how you should structure your variable names for readability and consistency. In Lua, there are several accepted naming conventions to choose from:

- camelCase: In camelCase, variable names begin with a lowercase letter, and each subsequent word within the name starts with a capital letter. The name resembles a camel's hump, hence the term "camelCase." Example: myVariable

- PascalCase: Similar to camelCase, but every word in the variable name starts with a capital letter. PascalCase is often used for naming classes, types, or modules in Lua. Example: MyVariable

- snake_case: In snake_case, words within the variable name are separated by underscores ('_'). This convention is commonly used in Lua for naming variables, functions, and other identifiers. Example: my_variable

- SCREAMING_SNAKE_CASE: This is a variation of snake_case where all letters are in uppercase, and words are still separated by underscores. It is typically used to represent constant values that should not be modified during the program's execution. Example: MY_CONSTANT_VALUE

It's a matter of personal preference which convention(s) you use, but personally, I use a mix of `PascalCase` and `camelCase`.

## Summary
As you can see, variables are essential and very useful for coding. They help reduce repetitive code and can actually benefit performance in some cases.
