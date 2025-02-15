Using `with open()` **automatically closes files**, preventing errors.

python

CopyEdit

`with open('myfile.txt', 'r') as file:     data = file.read()   # No need for file.close()`

✅ **Using `with` is the best practice for file handling.**