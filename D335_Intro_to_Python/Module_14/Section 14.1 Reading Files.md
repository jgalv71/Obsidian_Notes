### **📌 1️⃣ Opening and Reading Files**

The `open()` function is used to open files.

``` python
file = open('myfile.txt', 'r')  # 'r' means read mode 
contents = file.read()  # Reads entire file into a string 
file.close()  # Always close the file when done print(contents)
```

🔹 **Key Notes:**

- `'r'` = **read mode** (file must exist).
- **Always close** the file using `.close()` after reading.

💡 **Reading line by line:**

``` python
file = open('myfile.txt', 'r') 
for line in file:     
print(line.strip())  # Strip removes extra spaces/newlines file.close()`
```
✅ **This prevents loading an entire file into memory at once.**

🔹 **Alternative: Using `.readlines()` to store lines as a list**

``` python
file = open('myfile.txt', 'r') 
lines = file.readlines() 
file.close() 
print(lines)  # ['Line 1\n', 'Line 2\n']
```