### **📌 4️⃣ Reading & Writing Binary Files**

Some files (images, PDFs) contain **binary data** instead of text. Python can read/write these files using `'rb'` and `'wb'` modes.

🔹 **Reading a binary file**

python

CopyEdit

`file = open('image.jpg', 'rb')  # Read binary mode data = file.read() file.close() print(data[:20])  # Prints first 20 bytes`

🔹 **Writing binary data**

python

CopyEdit

`file = open('output.bin', 'wb') file.write(b'\x00\xFF\x01\x02')  # Writes raw bytes file.close()`

✅ **Binary mode is crucial for non-text files.**