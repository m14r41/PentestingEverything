# Source Vulnerable and Fix example

## Some common vulnrable code are mention below.


# Source Code Analysis
---
### > Vulnerable code Challenge:

## SQL Injection (SQLi)
- Vulnerable Code: Direct concatenation of user input into SQL query.
- Fix: Use parameterized queries to separate data from commands.

```python
import sqlite3

def get_user(username):
    conn = sqlite3.connect('database.db')
    cursor = conn.cursor()
    cursor.execute("SELECT * FROM users WHERE username = '" + username + "'")  # Vulnerable
    return cursor.fetchone() 
```

 - **Fixed Code**
```python
def get_user(username):
    conn = sqlite3.connect('database.db')
    cursor = conn.cursor()
    cursor.execute("SELECT * FROM users WHERE username = ?", (username,))  # Fixed
    return cursor.fetchone() 
```

## Server-Side Request Forgery (SSRF)
- Vulnerable Code: Direct use of user-controlled input in HTTP requests.
- Fix: Validate and restrict user-supplied URLs to prevent SSRF.
```python
import requests

def fetch_url(url):
    response = requests.get(url)  # Vulnerable
    return response.text
```

 -  **Fixed Code**
```python
def fetch_url(url):
    if not url.startswith('http://') and not url.startswith('https://'):
        raise ValueError('Invalid URL')
    response = requests.get(url)
    return response.text
```

## Cross-Site Scripting (XSS)
- Vulnerable Code: Rendering user input without proper escaping.
- Fix: Use escaping functions to prevent injection of malicious scripts.

```python
from flask import Flask, request, render_template_string, escape

app = Flask(__name__)

@app.route('/')
def index():
    name = request.args.get('name', 'Guest')
    return render_template_string('<h1>Hello, {{ name }}</h1>', name=name)  # Vulnerable
```

- **Fixed Code**

```python
 @app.route('/')
 def index():
    name = request.args.get('name', 'Guest')
    return render_template_string('<h1>Hello, {{ name | safe }}</h1>', name=escape(name))  # Fixed
```


## Cross-Site Request Forgery (CSRF)
- Vulnerable Code: Lack of CSRF token protection in forms.
- Fix: Include CSRF tokens in forms and AJAX requests.

```python
<form action="/transfer" method="post">
    <input type="hidden" name="csrf_token" value="{{ csrf_token }}">
    <input type="hidden" name="amount" value="1000">
    <input type="submit" value="Transfer Money">
</form>
```

## OS Command Injection
- Vulnerable Code: Direct use of user input in system commands without validation.
- Fix: Use subprocess module with proper input validation and sanitization.
```python
import subprocess

def execute_command(command):
    result = subprocess.check_output(command, shell=True, stderr=subprocess.STDOUT)  # Vulnerable
    return result.decode("utf-8")
```

 - **Fixed Code**
```py
def execute_command(command):
    try:
        result = subprocess.check_output(command, shell=True, stderr=subprocess.STDOUT)
        return result.decode("utf-8")
    except subprocess.CalledProcessError as e:
        return f"Error: {e}"
```

## Local File Inclusion (LFI)
- Vulnerable Code: Directly opens a file without proper validation.
- Fix: Check if the file exists before reading its content.
```python
def read_file(file_path):
    with open(file_path, 'r') as file:
        content = file.read()
    return content
```
 - **Fixed Code**
```py
def read_file_fixed(file_path):
    if not os.path.isfile(file_path):
        return "File not found"
    with open(file_path, 'r') as file:
        content = file.read()
    return content
```

## Remote File Inclusion (RFI)
- Vulnerable Code: Makes an HTTP request to a user-supplied URL without proper validation.
- Fix: Check if the URL starts with 'http://' or 'https://' and handle HTTP errors properly.
```python
def fetch_remote_file(url):
    if not filter_var($url, FILTER_VALIDATE_URL):
        throw new Exception('Invalid URL')
    return file_get_contents($url)
```
  - **Fixed Code**
```py
def fetch_remote_file(url):
    if not url.startswith(('http://', 'https://')):
        return "Invalid URL"
    response = requests.get(url)
    if response.status_code != 200:
        return "Failed to fetch remote file"
    return response.text

```
![image](https://github.com/m14r41/PentestingEverything/assets/95265573/f0a57773-4757-4e4d-8e58-8480598fba1e)

 What vulnerability do you see in this code?
👉 TIP: Try to go beyond File Upload issue and see how can that be escalated?
💡 HINT: Apache <br> credit **njmulsqb**

![image](https://github.com/m14r41/PentestingEverything/assets/95265573/c31cf443-7706-4b98-b262-25dd27036624)

