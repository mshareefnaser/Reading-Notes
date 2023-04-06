# Q: What is the purpose of the ‘with’ statement when opening a file in Python, and how does it help manage resources while reading and writing files?
The 'with' statement in Python is used to open a file and ensure that it is closed properly after it is used, even if an error occurs while accessing the file. This helps manage resources by freeing up system memory and preventing resource leaks. The 'with' statement provides a context in which the file is accessed, and when the code exits the context, the file is automatically closed, freeing up resources that were allocated to it. This means that you don't have to worry about manually closing the file, and you can be sure that it will be closed correctly, even in the event of an error.
# Q:Explain the difference between the ‘read()’ and ‘readline()’ methods for file objects in Python. Provide examples of when to use each method.
In Python, the read() and readline() methods are used to read data from a file object. The main difference between these two methods is the amount of data they read at a time.

The read() method reads the entire contents of the file as a string and returns it. If you don't pass any argument to the read() method, it reads the entire file. However, you can also pass an optional argument to specify the number of bytes to read. 
# Briefly describe the concept of exception handling in Python. How can the ‘try’, ‘except’, and ‘finally’ blocks be used to handle exceptions and ensure proper execution of code? Provide a simple example.

Exception handling in Python is a way to handle errors and exceptions that may occur during program execution. In Python, when an error or exception occurs, the program stops executing and raises an exception, which can be caught and handled by the code.

The try, except, and finally blocks are used in Python to handle exceptions and ensure proper execution of code. The try block contains the code that may raise an exception, and the except block contains the code to handle the exception if it is raised. The finally block contains the code that is always executed, regardless of whether an exception is raised or not.

```python 
try:
    x = int(input("Enter a number: "))
    y = int(input("Enter another number: "))
    result = x / y
    print("Result: ", result)
except ValueError:
    print("Invalid input. Please enter a valid integer.")
except ZeroDivisionError:
    print("Cannot divide by zero.")
finally:
    print("Execution complete.")

```