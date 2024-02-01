# 01 Python

### Official Documentation

[https://docs.python.org/3/contents.html](https://docs.python.org/3/contents.html)  

  

### One-Liners

[https://medium.com/python-in-plain-english/60-powerful-python-one-liners-for-everyday-coding-tasks-94cafe16ca85](https://medium.com/python-in-plain-english/60-powerful-python-one-liners-for-everyday-coding-tasks-94cafe16ca85)  

  

### Decorators

[https://medium.com/python-in-plain-english/mastering-python-decorators-a-comprehensive-guide-to-advanced-function-modification-9ce4fdc394d7](https://medium.com/python-in-plain-english/mastering-python-decorators-a-comprehensive-guide-to-advanced-function-modification-9ce4fdc394d7)  

  

  

### Data Wrangling

[https://medium.com/python-in-plain-english/beyond-the-list-mastering-pythons-powerful-tools-for-data-wrangling-79e05df28c9a](https://medium.com/python-in-plain-english/beyond-the-list-mastering-pythons-powerful-tools-for-data-wrangling-79e05df28c9a)  

  

### Medium Python Fundamentals

[https://medium.com/@pythonfundamentals](https://medium.com/@pythonfundamentals)

[https://medium.com/ai-genesis/my-personal-collection-of-10-python-decorators-one-liners-that-shaped-my-career-a012332a5e0c](https://medium.com/ai-genesis/my-personal-collection-of-10-python-decorators-one-liners-that-shaped-my-career-a012332a5e0c)  

  

### Pretty Printing

[https://medium.com/python-in-plain-english/python-print-magic-40-advanced-techniques-for-stylish-outputs-and-creative-coding-e13b6828cc2c](https://medium.com/python-in-plain-english/python-print-magic-40-advanced-techniques-for-stylish-outputs-and-creative-coding-e13b6828cc2c)

  

Examples:

  

```python
# pprint
from pprint import pprint
data = {'name': 'John', 'age': 30, 'city': 'New York'}
pprint(data)

#tqdm
from tqdm import tqdm
for i in tqdm(range(100)):
    # Some time-consuming operation
    pass

# tabulate
from tabulate import tabulate
data = [["Alice", 25], ["Bob", 30], ["Charlie", 35]]
print(tabulate(data, headers=["Name", "Age"]))

# rich.console
from rich.console import Console
console = Console()
console.print("[bold red]Error:[/bold red] Something went wrong!")

# colored
from termcolor import colored
print(colored('This is a warning!', 'yellow', attrs=['bold']))
```

#   

  

  

  

  

  

### Pylink

[https://medium.com/@kpatronas/python-use-pylint-to-make-better-code-8bc2e8b7a2b8](https://medium.com/@kpatronas/python-use-pylint-to-make-better-code-8bc2e8b7a2b8)  

  

```python
pip install pylint
pylink <python_file.py>
```

  

  

### Logging Module

[https://medium.com/@gaurav-adarshi/logging-module-in-python-a3ed49257928](https://medium.com/@gaurav-adarshi/logging-module-in-python-a3ed49257928)  

  

**Constants (all caps):**

- Constants are fixed values that represent log levels, such as DEBUG, INFO, WARNING, ERROR, and CRITICAL.

**Classes (capitalized):**

- Logger: An object that represents a logging channel and is responsible for emitting log messages.
- Handler: A class that defines where log messages are sent, like the console or a file.
- Filter: A class used to specify which log records should be processed based on certain criteria.

**Methods (start with lowercase letters):**

```
logger.info(msg): Logs an informational message with the INFO level.
logger.warning(msg): Logs a warning message with the WARNING level.
logger.error(msg): Logs an error message with the ERROR level.
logger.critical(msg): Logs a critical message with the CRITICAL level.
logger.log(lvl, msg): Logs a message with a custom integer log level (lvl).
logger.exception(msg): Logs an error message with the ERROR level and includes exception information.
logger.setLevel(lvl): Sets the minimum log level (threshold) for this logger, ignoring messages below that level.
logger.addFilter(filt): Adds a filter to this logger, allowing fine-grained control over which log records are processed.
logger.removeFilter(filt): Removes a specific filter from this logger.
logger.filter(record): Applies the logger's filter to a log record and returns True if it should be processed, otherwise False.
logger.addHandler(hdlr): Adds a log handler (output destination) to this logger.
logger.removeHandler(hdlr): Removes a specific log handler from this logger.
logger.hasHandlers(): Checks if the logger has any configured log handlers.
```

These methods and concepts are fundamental to the Python logging module, allowing you to control log levels, filters, handlers, and more for effective logging in your applications.

**Useful Handlers:**

In addition to the base Handler Class, many useful subclasses are provided.

```
StreamHandler: Sends messages to console or file-like objects.
FileHandler: Sends messages to files on disk.
RotatingFileHandler: Sends messages to files with size limits and automatic file rotation.
TimedRotatingFileHandler: Sends messages to files with time-based rotation.
SocketHandler: Sends messages over network sockets.
DatagramHandler: Sends messages over UDP sockets.
SMTPHandler: Sends messages to an email address.
SysLogHandler: Sends messages to a system log daemon.
NTEventLogHandler: Sends messages to Windows event logs.
MemoryHandler: Buffers messages in memory and flushes based on criteria.
HTTPHandler: Sends messages to an HTTP server.
WatchedFileHandler: Monitors and reopens log files when they change.
QueueHandler: Sends messages to a queue.
NullHandler: Ignores error messages, useful for library developers.
```

### Python Logging Basics:

To log events in a file using Python’s logging module, start by importing it from the library, and it’s quite straightforward.

Configure a logger by specifying a file name for event recording, adjust the format, switch between append and write modes, set a logging level threshold, and customize attributes from available options. Create an instance and utilize its methods as demonstrated in an example.

### Logging a Variable:

This code shows how to record a mistake message using the logging.error() function, which includes a spaceholder (%s) for the variable’s name.

```
import logging
name = 'Rocky'
logging.error(f'{name} raised an error')

Output:
ERROR:root:Rocky raised an error
```

### Logging of all the levels:

This code shows various levels of recording information.

```
# Import the logging module
import logging

# Create and configure the logger
logging.basicConfig(filename="newfile.log",  # Specify the log file name
                    format='%(asctime)s %(message)s',  # Define log message format
                    filemode='w')  # Set file mode to 'w' for writing

# Create a logger object
logger = logging.getLogger()

# Set the logger's threshold to DEBUG level
logger.setLevel(logging.DEBUG)

# Log different test messages with various severity levels
logger.debug("A harmless debug message")  # Debug level message
logger.info("Just providing some information")  # Information level message
logger.warning("This is a warning")  # Warning level message
logger.error("Have you attempted to divide by zero?")  # Error level message
logger.critical("The internet connection is down")  # Critical level message

Output:
DEBUG:root:A harmless debug message
INFO:root:Just providing some information
WARNING:root:This is a warning
ERROR:root:Have you attempted to divide by zero?
CRITICAL:root:The internet connection is down
```

### **An alternative representation of the provided logging configuration.**

```
file name : temp.conf

[loggers]
keys=root,simpleExample

[handlers]
keys=consoleHandler

[formatters]
keys=simpleFormatter

[logger_root]
level=DEBUG
handlers=consoleHandler

[logger_simpleExample]
level=DEBUG
handlers=consoleHandler
qualname=simpleExample
propagate=0

[handler_consoleHandler]
class=StreamHandler
level=DEBUG
formatter=simpleFormatter
args=(sys.stdout,)

[formatter_simpleFormatter]
format=%(asctime)s - %(name)s - %(levelname)s - %(message)s
```

  

The provided code initializes a logging system by utilizing settings specified in the ‘temp.conf’ configuration file. It proceeds to create a logger identified as ‘simpleExample’ and subsequently records messages using a range of log levels.

```
# my_logging.py

import logging
import logging.config

logging.config.fileConfig('temp.conf')

# create logger
logger = logging.getLogger('simpleExample')

# 'application' code
logger.debug('debug message')
logger.info('info message')
logger.warning('warn message')
logger.error('error message')
logger.critical('critical message')

Output:
2023-09-01 13:04:35,581 - simpleExample - DEBUG - debug message
2023-09-01 13:04:35,581 - simpleExample - INFO - info message
2023-09-01 13:04:35,581 - simpleExample - WARNING - warn message
2023-09-01 13:04:35,581 - simpleExample - ERROR - error message
2023-09-01 13:04:35,582 - simpleExample - CRITICAL - critical message
```

#### Python Logging Exception:

Using exceptions during logging can serve a valuable purpose in specific situations by signaling unusual circumstances or mistakes within your application. When an exception is raised, it acts as a red flag, interrupting the regular program flow and informing either the caller or the logging system about the encountered problem.

```
import logging

# Configure the logging system
logging.basicConfig(level=logging.DEBUG,
                    format='%(asctime)s - %(levelname)s - %(message)s')

# Define a function to perform an operation on a given value
def perform_operation(value):
    if value < 0:
        # Raise a ValueError for negative input
        raise ValueError("Invalid value: The value cannot be negative.")
    else:
        # Continue with the operation and log a success message
        logging.info("Operation completed successfully.")

try:
    # Get user input for a numerical value
    input_value = int(input("Please input a numerical value: "))
    
    # Call the perform_operation function with the input value
    perform_operation(input_value)
except ValueError as ve:
    # Handle a ValueError exception and log it
    logging.exception("An exception occurred: %s", str(ve))

Output:
Please input a numerical value: 
-6

ERROR:root:An exception occurred: Invalid value: The value cannot be negative.
Traceback (most recent call last):
  File "<ipython-input-15-d0b160f9076e>", line 21, in <cell line: 16>
    perform_operation(input_value)
  File "<ipython-input-15-d0b160f9076e>", line 11, in perform_operation
    raise ValueError("Invalid value: The value cannot be negative.")
ValueError: Invalid value: The value cannot be negative.
```

  

  

### .env files

[https://medium.com/python-in-plain-english/the-essentials-of-env-files-in-python-simplifying-environment-management-securing-your-secrets-14c51c411400](https://medium.com/python-in-plain-english/the-essentials-of-env-files-in-python-simplifying-environment-management-securing-your-secrets-14c51c411400)  

###   

### What is a .env File?

A `.env` file is a simple text file holding key-value pairs, used to manage environment variables like API keys and passwords. Each line represents a data entry, separating the variable name and value with an "=" sign.

  

Installation:

```
pip install python-dotenv
```

  

### Example: Using OpenAI API with .env File:

1. Create .env File: In your project directory, create a `.env` file:

```
OPENAI_API_KEY=your-openai-api-key
```

  

  2. Python Script:

This script demonstrates how to securely use an API key from a `.env` file for making authenticated requests to an external API, in this case, OpenAI. This method ensures sensitive information like API keys are not hard-coded into the source code, enhancing security and maintainability.

```
from dotenv import load_dotenv
import os
import requests

load_dotenv()  # Load .env file

openai_api_key = os.getenv('OPENAI_API_KEY')  # Get API key

url = "https://api.openai.com/v1/engines/davinci/completions"

headers = {"Authorization": f"Bearer {openai_api_key}"}

data = {
    "prompt": "Translate 'Hello, how are you?' to French.",
    "max_tokens": 60
}

response = requests.post(url, headers=headers, json=data)
print(response.json())
```

  

### Setting an Environment Variable:

- In Unix/Linux/macOS:

```
export VARIABLE_NAME=value
```

- In Windows Command Prompt:

```
set VARIABLE_NAME=value
```

- In Windows PowerShell:

```
$env:VARIABLE_NAME="value"
```

### Accessing the Environment Variable:

- In Unix/Linux/macOS:

```
echo $VARIABLE_NAME
```

- In Windows Command Prompt or PowerShell:

```
echo %VARIABLE_NAME%
```

- or

```
echo $env:VARIABLE_NAME
```

### In Python Code:

### Accessing an Environment Variable:

First, you need to import the `os` module, which provides a portable way of using operating system-dependent functionality.

```
import os  
variable_value = os.getenv('VARIABLE_NAME') 
print(variable_value)
```

The `os.getenv` function retrieves the value of the environment variable named `'VARIABLE_NAME'`. If the variable doesn't exist, `None` is returned. You can also provide a default value as a second argument to `os.getenv` which will be used if the variable isn’t found.

### Setting an Environment Variable (for use within the same script):

Although environment variables are typically set outside your Python script, sometimes you might want to set them from within the script.

```
os.environ['VARIABLE_NAME'] = 'value'
```

This sets the environment variable `'VARIABLE_NAME'` for the current script and any child processes started by the script. However, this change won't affect the environment outside of the script.

  

  

### Serialization Techniques

[https://medium.com/@gaurav-adarshi/serialization-techniques-in-python-297a4489ba87](https://medium.com/@gaurav-adarshi/serialization-techniques-in-python-297a4489ba87)  

  

## Techniques

  

- Pickle
- JSON
- Marshall
- Preference is JSON
- Sample JSON code:

  

## Examples

```
# Encoding Python objects into JSON
import json
data = {
   "name": "John",
   "age": 30,
   "city": "New York"
}
json_data = json.dumps(data)
print(json_data)

# Decoding JSON into Python objects
import json
json_data = '{"name": "John", "age": 30, "city": "New York"}'
data = json.loads(json_data)
print(data)

# Working with Files
import json
data = {
   "name": "John",
   "age": 30,
   "city": "New York"
}
with open('data.txt', 'w') as f:
   json.dump(data, f)

with open('data.txt', 'r') as f:
   data = json.load(f)
print(data)

# Handling Complex Data Types
import json
from datetime import datetime

def datetime_handler(obj):
   if isinstance(obj, datetime):
       return obj.isoformat()
   raise TypeError("Type %s not serializable" % type(obj))

data = {
   "name": "John",
   "age": 30,
   "birthday": datetime.now()
}

json_data = json.dumps(data, default=datetime_handler)
print(json_data)
```

  

  

  

### py to exe

[https://medium.com/@aalam-info-solutions-llp/convert-python-file-into-executable-file-exe-b91eb0665ab9](https://medium.com/@aalam-info-solutions-llp/convert-python-file-into-executable-file-exe-b91eb0665ab9)  

Suppose you’ve created a Python script that you want to provide to your client. In order to execute this code, your client must have Python installed on their system and possess a basic understanding of tasks such as installing necessary libraries and running Python scripts.

To simplify the process for your client and eliminate these prerequisites, it is advisable to convert or compile your Python code into an executable file, typically denoted by the .exe extension. This way, your client can simply double-click the .exe file, similar to other software, and your code will run without any additional steps or requirements.

**STEPS:**

1. Create the python file.
2. Install library.
3. Run the Exe File.
4. Conclusion

# **STEP1: Create a new python file:**

Create a separate folder in that create the new python file.

![](https://miro.medium.com/v2/resize:fit:700/1*235rCaRwLLfK0cLvGwNmFw.png)

Create a python file

I have developed a Login page using the Tkinter library to capture user input through a text box.

**Tkinter:**

Tkinter is a Python library for creating graphical user interfaces (GUIs). It comes bundled with Python installations, providing a simple and accessible way to build desktop applications. Tkinter supports various widgets, making it easy to design interactive interfaces for tasks ranging from basic scripts to more complex applications. Its cross-platform nature ensures compatibility across Windows, macOS, and Linux systems, making Tkinter a popular choice for GUI development in the Python ecosystem.

**Login page Code:**

```
from tkinter import messagebox

window = Tk()
window.title('Login')
window.geometry('600x250+100+100')

l1 = Label(window, text='UserName:', font=(14))
l2 = Label(window, text='Password:', font=(14))
l1.grid(row=0, column=0, padx=5, pady=5)
l2.grid(row=1, column=0, padx=5, pady=5)

userName  = StringVar()
password = StringVar()
t1 = Entry(window, textvariable=userName, font=(14))
t2 = Entry(window, textvariable=password, font=(14))
t1.grid(row=0, column=1)
t2.grid(row=1, column=1)

# Add a submit button

def login():
    try:

        if userName.get() == 'Admin' and password.get() == 'password':
             messagebox.showinfo(title='Status', message= "Login Success")

        else:
            messagebox.showinfo(title='Status', message= "Login Failed")

    except Exception as e:
         error_message = f'An error occurred: {str(e)}'

    

b1 = Button(window, command=login, text='Submit', font=(14))
b1.grid(row=2, column=1, sticky=W)

window.mainloop()
```

# **STEP 2: Install PyInstaller**

PyInstaller is a popular Python packaging tool that converts Python scripts or applications into standalone executables for various operating systems, including Windows, macOS, and Linux. This allows you to distribute your Python applications as standalone packages without requiring users to install Python or any additional dependencies.

User can install PyInstaller using pip:

Open a terminal or command prompt and run the following command to install PyInstaller

![](https://miro.medium.com/v2/resize:fit:700/1*x-EuY072Gb3HGPKh3cjbcA.png)

Install the pyInstaller

**Navigate to the Python file directory:**

Use the cd command to navigate to the directory where Python file is located.

![](https://miro.medium.com/v2/resize:fit:700/1*TxUosloIuvOZKf-RBpNUww.png)

Move to the directory of python code

**Create the executable:**

![](https://miro.medium.com/v2/resize:fit:667/1*Id0v9KWFZ-8MiLjCggQe-w.png)

Conversion of exe file

Replace your **Login.py** with the name of your Python file.

The — onefile flag tells PyInstaller to create a single executable file instead of a directory with multiple files.

Below is the entire process command log for your reference:

![](https://miro.medium.com/v2/resize:fit:700/1*P2wDjNub5wZRYMZTfQGMZQ.png)

Process logs

**To find the Exe File:**