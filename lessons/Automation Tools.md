## Automation Tools


Automation is one of the most powerful ways to save time, reduce errors, and streamline repetitive tasks. In this lesson, you'll learn the foundational Python modules that make everyday automation simple and reliable.

---

### 🚀 Concepts Covered

- **os**: Working with files and directories  
- **datetime**: Working with dates and times  
- **glob**: Pattern matching for file search  
- **shutil**: High-level file operations  
- **Practical automation**: Rename files, create folders, and clean up directories  

---

### 1. `os` — Working With Files and Directories

The `os` module lets you interact with your operating system.

### Common Tasks

- List files in a directory  
- Create or remove folders  
- Build file paths  
- Check if a file or folder exists  

### Examples

```python
import os

# List files
print(os.listdir("."))

# Create a folder
os.mkdir("reports")

# Join paths safely
path = os.path.join("reports", "summary.txt")
print(path)
```

2. `datetime`— Working With Dates and Times
Automation often involves timestamps, scheduling, or naming files with dates.

**Common Tasks**
- Get the current date/time

- Format dates for filenames

- Calculate time differences

**Examples**

```python
from datetime import datetime

now = datetime.now()
print(now)

# Format for filenames
stamp = now.strftime("%Y-%m-%d_%H-%M")
print(stamp)
```

3. `glob` **— Pattern Matching for File Search**
glob helps you find files using patterns (e.g., all .txt files).

**Common Tasks**
- Find all files of a certain type

- Search recursively

- Filter files by prefix or suffix

**Examples**
```python
import glob

# Find all text files
files = glob.glob("*.txt")
print(files)

# Recursive search
images = glob.glob("**/*.png", recursive=True)
print(images)
```

4. `shutil` **— High‑Level File Operations**
shutil handles copying, moving, and deleting files or directories.

**Common Tasks**
- Copy files

- Move files

- Delete folders

- Create compressed archives

**Examples**
```python
import shutil

# Copy a file
shutil.copy("data.csv", "backup/data.csv")

# Move a file
shutil.move("old/report.txt", "archive/report.txt")

# Delete a folder
shutil.rmtree("temp_folder")
```
5. **🛠 Practical Automation Projects**
A. Rename Files Automatically
```python
import os

for i, filename in enumerate(os.listdir("images")):
    new_name = f"image_{i}.jpg"
    os.rename(f"images/{filename}", f"images/{new_name}")
```
B. **Create Folders Based on Today’s Date**
```python
from datetime import datetime
import os

today = datetime.now().strftime("%Y-%m-%d")
os.makedirs(f"logs/{today}", exist_ok=True)
```
C. **Clean Up a Directory (Delete Temporary Files)**
```python
import glob
import os

for file in glob.glob("*.tmp"):
    os.remove(file)
```
### 🎯 Summary
By mastering these four modules — os, datetime, glob, and shutil — you unlock the ability to automate:

- File organization

- Backups

- Naming conventions

- Cleanup tasks

- Batch processing

These tools form the foundation of real-world automation in Python.