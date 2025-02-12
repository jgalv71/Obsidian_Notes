## **Why This is Important**
- When reading a problem statement, recognizing key **action words** can tell you **what programming concept to use**.
- This helps **break down problems faster** and choose the right tools in Python.

---

## **1️⃣ Handling User Input & Output**
| **Keyword in Problem**     | **What It Means in Python** | **Example Code**                    |
| -------------------------- | --------------------------- | ----------------------------------- |
| "Ask the user for..."      | Use `input()`               | `name = input("Enter your name: ")` |
| "Display on screen"        | Use `print()`               | `print("Hello, world!")`            |
| "Get an integer from user" | Use `int(input())`          | `age = int(input("Enter age: "))`   |

---

## **2️⃣ Conditional Statements (if-else)**
| **Keyword in Problem** | **What It Means in Python** | **Example Code** |
|------------------------|----------------------------|------------------|
| "If this happens, then..." | Use `if` statement | `if x > 10:` |
| "Otherwise" | Use `else` | `else:` |
| "Only if" | Use `if` without `else` | `if score >= 90:` |
| "If either A or B" | Use `or` operator | `if x == 5 or y == 10:` |
| "If both A and B" | Use `and` operator | `if x > 0 and y < 10:` |

---

## **3️⃣ Loops (Repeating Actions)**
| **Keyword in Problem** | **What It Means in Python** | **Example Code** |
|------------------------|----------------------------|------------------|
| "Repeat until..." | Use `while` loop | `while x < 10:` |
| "Do this for each..." | Use `for` loop | `for item in list:` |
| "Count from A to B" | Use `range()` | `for i in range(1, 6):` |
| "Keep asking until input is valid" | Use `while` with validation | `while user_input != "yes":` |

---

## **4️⃣ Lists (Handling Multiple Items)**
| **Keyword in Problem** | **What It Means in Python** | **Example Code** |
|------------------------|----------------------------|------------------|
| "A collection of values" | Use a **list** (`[]`) | `numbers = [1, 2, 3, 4]` |
| "Find the Nth item" | Use list indexing (`list[index]`) | `print(numbers[2])` |
| "Loop through all items" | Use `for` loop | `for num in numbers:` |
| "Add an item to the list" | Use `.append()` | `numbers.append(5)` |

---

## **5️⃣ Dictionaries (Key-Value Pairs)**
| **Keyword in Problem** | **What It Means in Python** | **Example Code** |
|------------------------|----------------------------|------------------|
| "Lookup by key" | Use a **dictionary** (`{}`) | `students = {"Alice": 90, "Bob": 85}` |
| "Find value for a given key" | Use `dict[key]` | `print(students["Alice"])` |
| "If key not found, handle it" | Use `.get()` or `try-except` | `print(students.get("Charlie", "Not found"))` |

---

## **6️⃣ Exception Handling (Handling Errors)**
| **Keyword in Problem** | **What It Means in Python** | **Example Code** |
|------------------------|----------------------------|------------------|
| "Might cause an error" | Use `try-except` | `try: x = int(input()) except ValueError:` |
| "If an error happens, show a message" | Use `print()` inside `except` | `print("Invalid input!")` |

---

## **Example: Applying This to a Word Problem**
**Problem Statement:**  
*"Ask the user to enter a number. If the number is greater than 10, print 'High'. Otherwise, print 'Low'."*

**Breaking It Down:**
- "Ask the user" → **Use `input()`**  
- "Enter a number" → **Convert input to `int()`**  
- "If the number is greater than 10" → **Use `if number > 10:`**  
- "Otherwise" → **Use `else:`**  
- "Print 'High' / 'Low'" → **Use `print()`**  

**Final Python Code:**
```python
number = int(input("Enter a number: "))

if number > 10:
    print("High")
else:
    print("Low")