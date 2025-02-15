**Key concepts:**

- Using `file.readlines()` to read file content.
- Using **string comparison** for range checking.
- **Sorting and filtering data in Python**.

### **📌 Lab 14.8: Words in a Range (Lists) - Step-by-Step Breakdown**

This lab requires us to **filter words** from a file, only keeping those that fall **within a specified alphabetical range**.

---

## **📖 Step 1: Understand the Input & Output**

### ✅ **Given Input:**

- The first input line is the **filename**.
- The second and third inputs are **lower and upper bounds** (strings).
- The file contains **a list of words**, one per line.

### ✅ **Expected Behavior:**

- Read the file contents.
- **Find words that fall alphabetically within the given range.**
- **Print the filtered words.**

---

## **📖 Step 2: Plan the Code Structure**

### 🔹 **1️⃣ Read the Input Data**

- Read the **filename** from user input.
- Read the **lower and upper bounds** for filtering.

### 🔹 **2️⃣ Open the File & Read the Words**

- Use `with open(filename, 'r')` to safely read the file.
- Use `.readlines()` to **store all words in a list**.

### 🔹 **3️⃣ Filter the Words**

- **Loop through each word in the file**:
    - Remove **extra spaces/newlines** with `.strip()`.
    - Use **string comparison (`>=` and `<=`)** to check if the word is within the range.

### 🔹 **4️⃣ Print the Words in Range**

- Print each word that falls **within the specified alphabetical range**.

---

## **📖 Step 3: Write the Code Step by Step**

### ✅ **1️⃣ Read the Inputs**
```python
filename = input()  # Read the filename
lower_bound = input().strip()  # Read the lower bound
upper_bound = input().strip()  # Read the upper bound
```


### ✅ **2️⃣ Read the File Contents**
``` python
with open(filename, 'r') as file:
    words = file.readlines()  # Read all words into a list
```
- `.readlines()` loads all words into a list.
- Each word has an **extra newline (`\n`)**, so we need to strip it later.

### ✅ **3️⃣ Process & Filter the Words**

```python
for word in words:
    word = word.strip()  # Remove whitespace/newlines
    if lower_bound <= word <= upper_bound:  # Check if within range
        print(word)  # Print only words that fit the range
```

- `.strip()` **removes extra spaces/newlines**.
- `if lower_bound <= word <= upper_bound:` **compares alphabetically**.

---

## **📖 Step 4: Full Code**

```python
# Read input values
filename = input()
lower_bound = input().strip()
upper_bound = input().strip()

# Open the file and read words
with open(filename, 'r') as file:
    words = file.readlines()

# Process & print words within range
for word in words:
    word = word.strip()  # Remove extra spaces/newlines
    if lower_bound <= word <= upper_bound:  # Alphabetical comparison
        print(word)
```

---

## **📌 Step 5: Test Cases**

### **Example 1**

#### ✅ **Input:**
```
input1.txt
ammoniated
millennium
```

✅ **Contents of `input1.txt`:**

```nginx
aspiration
classified
federation
graduation
millennium
philosophy
quadratics
transcript
wilderness
zoologists
```

✅ **Expected Output:**

```nginx
aspiration
classified
federation
graduation
millennium
```

---

### **📌 Step 6: Key Notes for Obsidian**

📄 **Create a new note:** `"14.8 Words in a Range (Lists)"`  
✏ **Include the following concepts:**

- **How to read files with `readlines()`**
- **How string comparisons work alphabetically (`<=` and `>=`)**
- **How to remove extra spaces with `.strip()`**
- **How to filter a list based on conditions**

### **📖 Step-by-Step Breakdown of the Example**

#### **✅ Given Input:**

```
input1.txt
ammoniated
millennium
```

#### **✅ Contents of `input1.txt`:**

```nginx
aspiration
classified
federation
graduation
millennium
philosophy
quadratics
transcript
wilderness
zoologists
```
#### **✅ What Happens in the Code?**

- We check **each word alphabetically** to see if it falls **between** `"ammoniated"` and `"millennium"` (inclusive).
- `"ammoniated"` is **not in the file**, but since `"aspiration"` comes **after** it alphabetically, it's included.
- `"millennium"` **is included** because the range is **inclusive** (`<=`).

#### **✅ Output:**

```nginx
aspiration
classified
federation
graduation
millennium
```

---

### **📌 Key Concept: How Python Compares Strings Alphabetically**

Python **compares strings alphabetically** based on Unicode order:

✅ **Lowercase and Uppercase matter!**

```python
print("apple" < "banana")  # True, because "a" comes before "b"
print("Zebra" < "apple")   # True, because uppercase "Z" comes before lowercase "a"
print("apple" < "Apple")   # False, because lowercase "a" comes AFTER uppercase "A" in Unicode
```

**💡 This means that `"Zebra"` would be considered smaller than `"apple"`, so case sensitivity can affect results.**

### **✅ How to Make It Case-Insensitive**

🔹 **Modify the condition by converting all words to lowercase using `.lower()`**

```python
for word in words:
    word = word.strip().lower()  # Convert word to lowercase
    if lower_bound.lower() <= word <= upper_bound.lower():  # Compare in lowercase
        print(word)
```

✅ **Now, all comparisons ignore case differences!**
