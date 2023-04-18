## Explain the concept of variable scope in Python and describe the difference between local and global scope. Provide an example illustrating the usage of both.

Variable scope in Python refers to where a variable can be accessed. 

- Local variables are defined within a function or block and can only be accessed within that scope. They are destroyed once the function or block completes execution.
- Global variables are defined outside of functions and can be accessed from anywhere in the code.

```python
global_var = 5

def example_function():
    local_var = 10
    print("local_var:", local_var)
    print("global_var inside function:", global_var)

example_function()
print("global_var outside function:", global_var)
```

## How do the global and nonlocal keywords work in Python, and in what situations might you use them?

- The `global` keyword indicates a variable as global, allowing it to be accessed from any part of the code.
- The `nonlocal` keyword indicates a variable as nonlocal, allowing it to be accessed from nested functions.

They are used in situations where you need to modify or access variables outside of their current scope.

## Describe the purpose and importance of Big O notation in the context of algorithm analysis.

Big O notation is a way to analyze and describe the performance of an algorithm in terms of its time and space complexity. It helps understand how the efficiency of an algorithm scales with input size, enabling informed decisions when choosing algorithms for different tasks.

## Based on the Rolling Dice Example, explain how you would simulate a dice roll using Python. Describe how you would use code to calculate the probability of rolling a specific number (e.g., the probability of rolling a 6) over a large number of trials.

To simulate a dice roll in Python, you can use the `random` module's `randint` function to generate a random number between 1 and 6. To calculate the probability of rolling a specific number (e.g., 6) over a large number of trials, you can divide the count of occurrences of the specific number by the total number of trials.