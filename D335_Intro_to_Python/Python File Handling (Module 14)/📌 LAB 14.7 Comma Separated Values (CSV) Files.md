
CSV files store tabular data in plain text with **commas separating values**.  
Example of a CSV file (`grades.csv`):

cpp

CopyEdit

`name,hw1,hw2,midterm,final Petr Little,9,8,85,78 Sam Tarley,10,10,99,100 Joff King,4,2,55,61`

#### **📖 How to Read CSV Files in Python**

Python's `csv` module makes it easy to read and write CSV files.

python

CopyEdit

`import csv  with open('grades.csv', 'r') as csvfile:     grades_reader = csv.reader(csvfile, delimiter=',')          for row in grades_reader:         print(row)  # Each row is a list of values`

#### **📖 How to Write to a CSV File**

python

CopyEdit

`import csv  data = [['100', '50', '29'], ['76', '32', '330']]  with open('gradeswr.csv', 'w') as csvfile:     grades_writer = csv.writer(csvfile)     grades_writer.writerows(data)`