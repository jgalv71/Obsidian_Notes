
### Error: `ValueError: invalid literal for int()`
- **What happened?** Entered text instead of a number.
- **Fix:** Used `try-except` to handle invalid input.
```python
try:
    age = int(input("Enter age: "))
except ValueError:
    print("Invalid input! Please enter a number.")
```

## Error: `IndexError: list index out of range`

- **What happened?** The user entered an index outside the valid range.

- **Fix:** Used `try-except` to catch the error and return a default value.

```python

try:

    print(names[index])

except IndexError:

    print("Out of range! Returning closest name.")

    print(names[-1])  # Last name as fallback
    ```

---

## 🐍 Python Syntax Errors & Fixes

### ❌ **SyntaxError: expected 'except' or 'finally' block**

**🔹 What This Means:**  

- Python **expects an `except` or `finally` block** right after `try`.  

- This usually happens if a statement (like `print()`) is **accidentally placed outside `try` but before `except`**.
### ✅ **How to Fix It**

#### **❌ Incorrect Code (Causes Error)**:

```python

try:

    x = int(input("Enter a number: "))

print(x)  # ❌ This is outside try and before except, causing an error

  

except ValueError:

    print("Invalid input!")```
  
### **✔ Correct Code (Fixed)**
  ```python
   try:

    x = int(input("Enter a number: "))

    print(x)  # ✅ Move inside try block

except ValueError:

    print("Invalid input!")
```

**💡 Lesson Learned** 
✅ Always make sure **all operations that could fail are inside the try block**.

✅ The except block **must follow try immediately** with nothing in between.

✅ If you need to use print() or another statement after try, **move it inside the try block**.

---


