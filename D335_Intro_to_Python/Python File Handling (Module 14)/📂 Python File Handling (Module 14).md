## 📝 Overview
Python provides powerful tools for **reading, writing, and managing files**. This module covers:
- Reading and writing files (`open`, `read`, `write`)
- File modes (`r`, `w`, `a`, etc.)
- OS module (interacting with the file system)
- Binary file handling
- CSV file handling
- Command-line arguments (`sys.argv`)

---
## 📖 1️⃣ Reading and Writing Files
### 🔹 Opening a File
```python
file = open("example.txt", "r")  # Open file in read mode
```
| Mode  | Description |
|--------|-------------|
| `"r"` | Read (default) |
| `"w"` | Write (overwrite file) |
| `"a"` | Append |
| `"rb"` | Read binary |
| `"wb"` | Write binary |

### 🔹 Reading a File
```python
with open("example.txt", "r") as file:
    content = file.read()  # Reads entire file
```
```python
with open("example.txt", "r") as file:
    lines = file.readlines()  # Reads file line by line into a list
```

### 🔹 Writing to a File
```python
with open("output.txt", "w") as file:
    file.write("Hello, Python!")
```

### 💡 Troubleshooting
✅ **Use `with open()`** to automatically close the file after reading/writing.
✅ **`w` mode erases the file contents**—use `a` to append instead.

---
## 📂 2️⃣ OS Module: Interacting with File System

```python
import os
print(os.getcwd())  # Get current directory
print(os.path.exists("example.txt"))  # Check if file exists
```
| Function | Description |
|----------|-------------|
| `os.getcwd()` | Get current working directory |
| `os.path.exists(filename)` | Check if file exists |
| `os.remove(filename)` | Delete a file |
| `os.path.getsize(filename)` | Get file size |


---
## 🖼️ 3️⃣ Binary Files (Images, PDFs, etc.)
```python
with open("image.jpg", "rb") as file:
    data = file.read()
    print(data[:20])  # Print first 20 bytes
```
**Use Cases:** Handling **images, videos, or PDFs** in Python.

---
## 📝 4️⃣ CSV Files (Spreadsheet Data)
### 🔹 Reading a CSV File
```python
import csv
with open("grades.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)  # Prints each row as a list
```

### 🔹 Writing a CSV File
```python
import csv
with open("output.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerow(["Name", "Score"])
    writer.writerow(["Alice", 95])
```

---
## ⌨️ 5️⃣ Command-Line Arguments (`sys.argv`)
```python
import sys
if len(sys.argv) > 1:
    filename = sys.argv[1]
    with open(filename, "r") as file:
        print(file.read())
```
**Use Case:** Passing filenames dynamically when running Python scripts.

---
## ✅ Best Practices
✅ Always close files after use (or use `with open()`).
✅ Use `try-except` blocks for error handling in file operations.
✅ When handling large files, read data **line-by-line** (`readline()` or `readlines()`).

---
### 🔗 Related Notes
- [[Python Basics]]
- [[Error Handling in Python]]
- [[Working with Data in Python]]
