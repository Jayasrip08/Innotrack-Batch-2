# Software Installation Guide (For Beginners)

Before starting the project, make sure all the required software is installed properly.

---

# Step 1: Install Python

### Download Python

Visit:

https://www.python.org/downloads/

Download the latest stable version of Python (3.12 or above).

### Important During Installation

While installing, make sure you select:

✅ **Add Python to PATH**

Then click:

**Install Now**

---

### Verify Python Installation

Open **Command Prompt** and run:

```cmd
python --version
```

You should see output similar to:

```cmd
Python 3.12.4
```

Now check pip:

```cmd
pip --version
```

Example:

```cmd
pip 24.x.x
```

---

# Step 2: Install Visual Studio Code

Download VS Code from:

https://code.visualstudio.com/

Install it using the default settings.

---

# Step 3: Install VS Code Extensions

Open VS Code.

Go to:

**Extensions → Search**

Install the following extensions:

### Required Extensions

✅ Python (Microsoft)

✅ SQLite Viewer

✅ Live Server

✅ Material Icon Theme (Optional)

✅ Auto Rename Tag (Optional)

---

# Step 4: Install Git

Download Git:

https://git-scm.com/downloads

Install using default settings.

Verify installation:

```cmd
git --version
```

---

# Step 5: Create Project Folder

Open Command Prompt.

Move to Desktop:

```cmd
cd Desktop
```

Create project folder:

```cmd
mkdir PersonalExpenseTracker
```

Move inside folder:

```cmd
cd PersonalExpenseTracker
```

Open in VS Code:

```cmd
code .
```

If `code` command is not recognized:

Open VS Code manually.

Select:

```text
File → Open Folder → PersonalExpenseTracker
```

---

# Step 6: Create Virtual Environment

Inside the terminal execute:

```cmd
python -m venv venv
```

This creates an isolated Python environment.

---

# Step 7: Activate Virtual Environment

### Windows

```cmd
venv\Scripts\activate
```

You should see:

```cmd
(venv)
```

before the terminal path.

---

### macOS/Linux

```bash
source venv/bin/activate
```

---

# Step 8: Install Flask

Install Flask:

```cmd
pip install flask
```

Verify installation:

```cmd
pip list
```

You should see:

```cmd
Flask
Werkzeug
Jinja2
click
itsdangerous
blinker
```

---

# Step 9: Create Project Structure

Create the following folders and files.

```text
PersonalExpenseTracker
│
├── app.py
├── expense.db
├── requirements.txt
│
├── templates
│   ├── index.html
│   ├── add_expense.html
│   ├── expenses.html
│   ├── edit_expense.html
│   └── summary.html
│
└── static
    ├── css
    │   └── style.css
    │
    ├── js
    │   └── script.js
    │
    └── images
```

---

# Step 10: Install SQLite Viewer

SQLite already comes built into Python.

No separate installation is required.

To verify:

Open Python:

```cmd
python
```

Then execute:

```python
import sqlite3
print(sqlite3.sqlite_version)
```

Example output:

```cmd
3.x.x
```

Exit Python:

```python
exit()
```

---

# Step 11: Create Requirements File

Generate dependency file:

```cmd
pip freeze > requirements.txt
```

This file will help recreate the project later.

---

# Step 12: Run Flask Project

Execute:

```cmd
python app.py
```

If everything works correctly, you will see:

```cmd
Running on http://127.0.0.1:5000
```

Open browser:

```text
http://127.0.0.1:5000
```

---

# Common Errors and Solutions

### Error:

```cmd
'python' is not recognized
```

### Solution:

Reinstall Python and enable:

✅ Add Python to PATH

---

### Error:

```cmd
'pip' is not recognized
```

### Solution:

Restart Command Prompt after installing Python.

---

### Error:

```cmd
No module named flask
```

### Solution:

Install Flask again:

```cmd
pip install flask
```

---

### Error:

```cmd
'code' is not recognized
```

### Solution:

Open VS Code.

Press:

```text
Ctrl + Shift + P
```

Search:

```text
Shell Command: Install 'code' command in PATH
```

Restart terminal.

---

# Final Verification Checklist

✅ Python Installed

✅ VS Code Installed

✅ Git Installed

✅ Virtual Environment Created

✅ Flask Installed

✅ Project Folder Created

✅ SQLite Working

✅ Application Running Successfully
