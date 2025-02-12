## 🔹 What is Exception Handling?

- Exception handling prevents **program crashes** when errors occur.

- It allows the program to **handle issues gracefully** instead of stopping execution.

  

## 🔹 Why Use `try-except`?

✅ Helps catch **invalid input errors**.  

✅ Prevents **unexpected crashes** when working with **user input**.  

✅ **Example: Handling user input errors**

```python

try:

    num = int(input("Enter a number: "))

    print(f"You entered: {num}")

except ValueError:

    print("That's not a valid number! Try again.")