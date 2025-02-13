### **📌 3️⃣ Working with File Paths**

Python’s `os` and `os.path` modules help manage file paths efficiently.

🔹 **Getting the current directory**

python

CopyEdit

`import os print(os.getcwd())  # Shows current working directory`

🔹 **Checking if a file exists**

python

CopyEdit

`import os print(os.path.exists('myfile.txt'))  # Returns True/False`

🔹 **Joining file paths (cross-platform)**

python

CopyEdit

`import os file_path = os.path.join('folder', 'myfile.txt') print(file_path)  # Windows: "folder\myfile.txt", Mac/Linux: "folder/myfile.txt"`

🔹 **Getting the size of a file**

python

CopyEdit

`import os print(os.path.getsize('myfile.txt'))  # Returns file size in bytes`