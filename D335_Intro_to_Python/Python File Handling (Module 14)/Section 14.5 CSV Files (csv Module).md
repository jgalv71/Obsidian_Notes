### **📌 5️⃣ Working with CSV Data**

CSV (Comma-Separated Values) files are commonly used for data storage. Python’s `csv` module makes it easy to read/write them.

🔹 **Reading a CSV file**

python

CopyEdit

`import csv with open('data.csv', 'r') as file:     reader = csv.reader(file)     for row in reader:         print(row)  # Prints each row as a list`

🔹 **Writing to a CSV file**

python

CopyEdit

`import csv data = [['Name', 'Age'], ['Alice', 25], ['Bob', 30]] with open('output.csv', 'w', newline='') as file:     writer = csv.writer(file)     writer.writerows(data)`

✅ **CSV files are useful for structured data.**