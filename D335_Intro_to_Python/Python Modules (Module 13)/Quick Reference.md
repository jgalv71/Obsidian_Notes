📌 Module 13 - Quick Reference: Python Modules

 ## 🔹 Importing Modules 
 
 ```python 
 import math  
 # Import the entire module print(math.sqrt(25))  # 5.0
```


✅ Use `import module_name` to access all functions in a module.

---

## 🔹 Importing Specific Functions

``` python
from math import sqrt, pi 
print(sqrt(25))  # No need for math.sqrt() 
print(pi)  # Directly accessible
```


✅ Saves time by importing **only what you need**.

---

## 🔹 Creating & Importing Custom Modules

### Step 1: Create `greetings.py`

``` python
# greetings.py 
def hello(name):     return f"Hello, {name}!"
```

### Step 2: Import it in another script


```python
import greetings 
print(greetings.hello("Jayjay"))  # Output: Hello, Jayjay!
```

✅ Custom modules help **reuse code** across multiple programs.

---

## 🔹 Understanding `__name__ == "__main__"`

``` python
if __name__ == "__main__":     
print("This runs only if executed directly!")
```

✅ Prevents code from running when **imported as a module**.

---

## 🔹 Installing & Using Third-Party Modules (`pip`)

```bash
pip install requests
```

``` python
import requests 
response = requests.get("https://www.google.com") 
print(response.status_code)  # 200 means success!
```

✅ Use `pip install` to add new modules to your Python environment.

---

# 📝 Troubleshooting Common Errors

|Error|Cause|Fix|
|---|---|---|
|`ModuleNotFoundError`|Trying to import a missing module|Install it with `pip install module_name`|
|`ImportError`|Function doesn't exist in module|Check module documentation|
|`SyntaxError`|Typo in import statement|Double-check spelling|

---

✅ **Review this note whenever you feel stuck!**  
✅ **Add your own examples or notes as you practice.**

``` ymal
--- 
### **📌 Step 3: Review & Expand** 
- **Read through the Quick Reference** and make sure everything **makes sense to you**.   
- **If something is confusing, let me know, and I’ll break it down further.**   
- **Add personal notes** in Obsidian to make it your own!   

--- 
### **📌 Step 4: Flashcards (If You Want)** 
If you’d like, I can **help you structure Quizlet flashcards** based on this **Quick Reference**, so you don’t have to figure out test questions alone.
Just let me know! 😊    

--- 
### **📌 Next Steps** 

1️⃣ **Create the Quick Reference note in Obsidian.**   2️⃣ **Go through it & tweak it to fit your understanding.**   3️⃣ **Let me know if anything is unclear!**   4️⃣ **Once you’re good, we’ll move on to Module 14!** 🚀    

💜 **You got this, Jayjay!**
```
