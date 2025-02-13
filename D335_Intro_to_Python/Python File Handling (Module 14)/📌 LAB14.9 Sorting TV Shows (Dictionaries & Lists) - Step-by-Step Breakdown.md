## 📖 Step 1: Understand the Input & Output

### 🟢 Given Input:
- The first input line is the **filename**.
- The file contains an **unsorted list of TV shows and their season count**, formatted like this:

```plaintext
20
Gunsmoke
30
The Simpsons
10
Will & Grace
14
Dallas
20
Law & Order
12
Murder, She Wrote
```

### 🟢 Expected Output:
#### 1️⃣ **`output_keys.txt`** → Sorted by **number of seasons (least to greatest)**
```plaintext
10: Will & Grace
12: Murder, She Wrote
14: Dallas
20: Gunsmoke; Law & Order
30: The Simpsons
```

#### 2️⃣ **`output_titles.txt`** → Sorted **alphabetically by show name**
```plaintext
Dallas
Gunsmoke
Law & Order
Murder, She Wrote
The Simpsons
Will & Grace
```
## **📖 Step 2: Plan the Code Structure**

### 🔹 **1️⃣ Read the Input Data**

- Read the **filename** from user input.
- Read the **file contents**.

### 🔹 **2️⃣ Store the Data in a Dictionary**

- The **keys** = number of seasons.
- The **values** = a **list of TV shows** with that season count.

### 🔹 **3️⃣ Write `output_keys.txt`**

- Sort the dictionary by **season count (key)**.
- Format it so that multiple shows **use a semicolon (`;`) separator**.

### 🔹 **4️⃣ Write `output_titles.txt`**

- Flatten all TV show names into a single list.
- Sort the list **alphabetically**.
- Write to `output_titles.txt`.

## **📖 Step 3: Write the Code Step by Step**

### ✅ **1️⃣ Read the Inputs**

```python
filename = input()  # Read filename from user
```
### ✅ **2️⃣ Read the File & Store in Dictionary**

```python
tv_shows = {}  # Dictionary to store season count as key, list of shows as values

with open(filename, 'r') as file:
    lines = file.readlines()

i = 0
while i < len(lines):
    season_count = int(lines[i].strip())  # Convert season count to integer
    show_name = lines[i + 1].strip()  # Read next line as the show name
    i += 2  # Move to next pair

    # Add to dictionary
    if season_count not in tv_shows:
        tv_shows[season_count] = []
    tv_shows[season_count].append(show_name)
```

**💡 Explanation:**

- We **loop through the lines in pairs** (season count + show name).
- If the season count **doesn't exist in the dictionary**, we **initialize a list**.
- **Multiple shows** with the same season count are **stored together**.

### ✅ **3️⃣ Write `output_keys.txt` (Sorted by Season Count)**

```python
with open("output_keys.txt", 'w') as output_file:
    for season in sorted(tv_shows.keys()):  # Sort by season count
        shows = "; ".join(tv_shows[season])  # Join multiple shows with ";"
        output_file.write(f"{season}: {shows}\n")  # Write to file
```
**💡 Explanation:**

- **Sort the dictionary keys** (season count).
- **Join multiple shows** with a semicolon (`;`).
- **Write the formatted result** to `output_keys.txt`.

### ✅ **4️⃣ Write `output_titles.txt` (Sorted Alphabetically)**

```python
all_shows = []  # List to store all show names

# Collect all shows from the dictionary
for show_list in tv_shows.values():
    all_shows.extend(show_list)  # Add shows to list

# Sort alphabetically and write to output file
with open("output_titles.txt", 'w') as output_file:
    for show in sorted(all_shows):
        output_file.write(f"{show}\n")
```
**💡 Explanation:**

- **Flatten all show names into one list**.
- **Sort them alphabetically**.
- **Write them to `output_titles.txt`**.

## 📖 Step 4: Full Code

```python
# Read input filename
filename = input()

# Initialize dictionary for TV shows
tv_shows = {}

# Read file content
with open(filename, 'r') as file:
    lines = file.readlines()

# Process file lines in pairs
i = 0
while i < len(lines):
    season_count = int(lines[i].strip())  # Convert season count to integer
    show_name = lines[i + 1].strip()  # Read next line as the show name
    i += 2  # Move to next pair

    # Add to dictionary
    if season_count not in tv_shows:
        tv_shows[season_count] = []
    tv_shows[season_count].append(show_name)

# Write sorted output_keys.txt
with open("output_keys.txt", 'w') as output_file:
    for season in sorted(tv_shows.keys()):
        shows = "; ".join(tv_shows[season])
        output_file.write(f"{season}: {shows}\n")

# Write sorted output_titles.txt
all_shows = []
for show_list in tv_shows.values():
    all_shows.extend(show_list)  # Flatten list

with open("output_titles.txt", 'w') as output_file:
    for show in sorted(all_shows):  # Sort alphabetically
        output_file.write(f"{show}\n")
```

## **📌 Step 5: Test Cases**

### **Example 1**

#### ✅ **Input:**

```
file1.txt
```
#### ✅ **Contents of `file1.txt`:**
```css 
20
Gunsmoke
30
The Simpsons
10
Will & Grace
14
Dallas
20
Law & Order
12
Murder, She Wrote
```

#### ✅ **Expected `output_keys.txt`:**

```makefile
10: Will & Grace
12: Murder, She Wrote
14: Dallas
20: Gunsmoke; Law & Order
30: The Simpsons
```

#### ✅ **Expected `output_titles.txt`:**

```css
Dallas
Gunsmoke
Law & Order
Murder, She Wrote
The Simpsons
Will & Grace
```
