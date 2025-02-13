This lab requires reading student information from a **tab-separated values (TSV) file**, computing **average grades**, assigning **letter grades**, and writing the output to a **new text file**.

---

### **📌 Steps to Solve Lab 14.10**

#### **Step 1: Read the TSV file name from the user**

- Ask the user for the file name.
- Open the file in **read mode**.

#### **Step 2: Read student data from the file**

- Each row contains:  
```makefile
Last Name, First Name, Midterm1 score, Midterm2 score, Final score
```
#### **Step 3: Process Student Data**

- **Compute the average exam score** for each student.
- **Assign a letter grade** using the following scale:
```makefile
A: 90 ≤ x
B: 80 ≤ x < 90
C: 70 ≤ x < 80
D: 60 ≤ x < 70
F: x < 60
```

#### **Step 4: Compute Exam Averages**

- Calculate the **average of each exam** across all students.

#### **Step 5: Write to Output File (`report.txt`)**

- Write **each student's name, exam scores, and letter grade**.
- Append **exam averages** at the end.

---

### **📌 Example Input & Output**

#### **Input (`StudentInfo.tsv`):**

```nginx
Barrett    Edan    70  45  59
Bradshaw   Reagan  96  97  88
Charlton   Caius   73  94  80
Mayo       Tyrese  88  61  36
Stern      Brenda  90  86  45
```
#### **Expected Output (`report.txt`):**

```css
Barrett    Edan    70  45  59  F
Bradshaw   Reagan  96  97  88  A
Charlton   Caius   73  94  80  B
Mayo       Tyrese  88  61  36  D
Stern      Brenda  90  86  45  C

Averages: midterm1 83.40, midterm2 76.60, final 61.60
```

### **📌 Code Breakdown (Step-by-Step)**

Here’s a structured way to approach this in Python:

```python
# Step 1: Ask user for filename
filename = input()

# Step 2: Open the TSV file and read contents
with open(filename, 'r') as file:
    lines = file.readlines()

students = []  # List to store student records
midterm1_scores = []
midterm2_scores = []
final_scores = []

# Step 3: Process student data
for line in lines:
    data = line.split()  # Splitting by whitespace
    last_name = data[0]
    first_name = data[1]
    mid1, mid2, final = map(int, data[2:])

    # Calculate average
    avg = (mid1 + mid2 + final) / 3

    # Determine letter grade
    if avg >= 90:
        grade = 'A'
    elif avg >= 80:
        grade = 'B'
    elif avg >= 70:
        grade = 'C'
    elif avg >= 60:
        grade = 'D'
    else:
        grade = 'F'

    # Store student info
    students.append(f"{last_name}\t{first_name}\t{mid1}\t{mid2}\t{final}\t{grade}")

    # Collect scores for exam averages
    midterm1_scores.append(mid1)
    midterm2_scores.append(mid2)
    final_scores.append(final)

# Step 4: Compute exam averages
avg_mid1 = sum(midterm1_scores) / len(midterm1_scores)
avg_mid2 = sum(midterm2_scores) / len(midterm2_scores)
avg_final = sum(final_scores) / len(final_scores)

# Step 5: Write output to "report.txt"
with open("report.txt", 'w') as output_file:
    for student in students:
        output_file.write(student + "\n")
    
    # Write exam averages
    output_file.write(f"\nAverages: midterm1 {avg_mid1:.2f}, midterm2 {avg_mid2:.2f}, final {avg_final:.2f}\n")
```
