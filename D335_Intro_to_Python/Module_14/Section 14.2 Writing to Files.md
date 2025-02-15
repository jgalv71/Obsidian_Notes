📌 2️⃣  Writing & Appending Data

Python allows you to **write to files** using `'w'` or `'a'`:

🔹 **Writing (`'w'` mode): Overwrites the file**
```python 
file = open('output.txt', 'w')
file.write("Hello, world!\n")  # Writes a string
file.close()
```
➡ If `output.txt` exists, this **overwrites** its contents!

🔹 **Appending (`'a'` mode): Adds to the file**
```python 
file = open('output.txt', 'a')
file.write("Adding another line.\n" #Adds instead of overwriting)
file.close()
```
✅ **Appending ensures previous content is not lost.**

🔹 **Writing multiple lines using `.writelines()`**

``` python
lines = ["Line 1\n", "Line 2\n", "Line 3\n"] 
file = open('output.txt', 'w') 
file.writelines(lines)  # Writes multiple lines at once 
file.close()
```

