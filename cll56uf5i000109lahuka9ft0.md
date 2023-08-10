---
title: "Basics of Python for Beginners"
datePublished: Thu Aug 10 2023 13:21:42 GMT+0000 (Coordinated Universal Time)
cuid: cll56uf5i000109lahuka9ft0
slug: basics-of-python-for-beginners
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691673532906/74d954e6-5385-48f5-8efc-6fc33ac2d1fc.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691673635014/dc5bdffa-f63a-48f0-93aa-a8372bc86ba4.png
tags: python, python3, devops, codenewbies, python-beginner

---

### ***What is Python?***

Python is a high-level, interpreted programming language known for its simplicity, readability, and versatility. It was created by Guido van Rossum and was first released in 1991. Python emphasizes code readability, making it easier for programmers to express concepts in fewer lines of code compared to languages like C++ or Java.

***Key features of Python: -***

1. **Readable Syntax:** Python uses indentation to define code blocks, which enforces a clean and consistent structure. This design choice enhances the readability of the code.
    
2. **Interpreted:** Python code is executed line by line by an interpreter, rather than being compiled into machine code. This leads to quicker development and easier debugging.
    
3. **Dynamic Typing:** Python is dynamically typed, meaning you don't need to declare variable types explicitly. The interpreter determines the type of a variable at runtime.
    
4. **Object-Oriented:** Python supports object-oriented programming (OOP) principles, allowing you to define classes and create objects with attributes and methods.
    
5. **Large Standard Library:** Python comes with a comprehensive standard library that provides modules and functions for various tasks, ranging from file handling and regular expressions to web development and data analysis.
    
6. **Cross-Platform:** Python is available on various operating systems, including Windows, macOS, and Linux. This cross-platform compatibility makes it easy to develop and run Python programs on different systems.
    
7. **Extensible:** Python can be extended with C or C++ code, allowing you to optimize critical sections of your program or interface with existing libraries.
    
8. **Community and Ecosystem:** Python has a large and active community that contributes to a wide range of third-party libraries and frameworks. This ecosystem covers domains such as web development (Django, Flask), data science (NumPy, pandas), machine learning (TensorFlow, PyTorch), and more.
    
9. **Multi-Purpose:** Python is used in various domains, including web development, scripting, scientific computing, data analysis, artificial intelligence, machine learning, automation, and more.
    
    ### ***How to Install Python?***
    
    here are the few steps, which are required for the installation of Python: -
    
    1. **Visit the Official Website:** Go to the official Python website at [**https://www.python.org/downloads/**](https://www.python.org/downloads/) in your web browser.
        
    2. **Choose a Version:** Python has multiple versions available, but it's recommended to choose the latest version from the Python 3. x series (e.g., Python 3.9). Python 3. x is the current and actively maintained version.
        
    3. **Download the Installer:** On the Python website, click on the "Downloads" tab. You'll see various download options for different platforms (Windows, macOS, Linux). Choose the installer that matches your operating system.
        
    4. **Run the Installer:**
        
        * **Windows:** Double-click the downloaded installer executable (usually named something like `python-3.9.6.exe`). Check the box that says "Add Python 3.9 to PATH" during the installation process. This will make it easier to run Python from the command line.
            
        * **macOS:** Double-click the downloaded installer package (usually named something like `python-3.9.6-macosx10.9.pkg`). Follow the on-screen instructions to complete the installation.
            
        * **Linux:** Python is often pre-installed on Linux systems. To check if Python is already installed, open a terminal and type `python3 --version`. If it's not installed, you can use your package manager to install it.
            
    
    ### ***Task 1: -* Install Python in your respective OS, and check the version.**
    
    To install Python on Linux, use the command
    
    ```bash
    sudo apt-get install python3.6
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691668159501/bdba0a70-f8d5-4460-9332-24219e00b347.png?auto=compress,format&format=webp align="left")
    
    Once the python is installed, check the version
    
    ```python
    python --version
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691668249059/a27b5e1b-fa9a-44e4-a369-ddbf03d4b641.png?auto=compress,format&format=webp align="left")
    
    ### *Task 2: -* Read about different Data Types in Python.
    
    The different Data Types in Python are as follows: -
    
    1. **Numeric Types:**
        
        * `int`: Represents integers (whole numbers), e.g., 5, -10, 1000.
            
        * `float`: Represents floating-point numbers (decimal numbers), e.g., 3.14, -0.5, 2.0.
            
    2. **Text Type:**
        
        * `str`: Represents strings, which are sequences of characters enclosed in single (' ') or double (" ") quotes, e.g., "Hello, World!", 'Python'.
            
    3. **Boolean Type:**
        
        * `bool`: Represents Boolean values, which can be either `True` or `False`. Used for logical operations and control flow.
            
    4. **Sequence Types:**
        
        * `list`: Represents ordered, mutable sequences. Lists can contain a mix of different data types, e.g., `[1, 2, "three", 4.0]`.
            
        * `tuple`: Represents ordered, immutable sequences. Similar to lists, but once created, their elements cannot be changed, e.g., `(1, 2, 3)`.
            
        * `range`: Represents an immutable sequence of numbers, often used in loops, e.g., `range(5)` creates the sequence \[0, 1, 2, 3, 4\].
            
    5. **Mapping Type:**
        
        * `dict`: Represents dictionaries, which are unordered collections of key-value pairs. Keys are unique and used to access corresponding values, e.g., `{"name": "Alice", "age": 25}`.
            
    6. **Set Types:**
        
        * `set`: Represents unordered collections of unique elements. Sets are mutable and can contain various data types, e.g., `{1, 2, 3}`.
            
        * `frozenset`: Represents immutable sets, similar to sets but cannot be modified after creation.
            
    7. **Binary Types:**
        
        * `bytes`: Represents immutable sequences of bytes, often used for binary data, e.g., `b'hello'`.
            
        * `bytearray`: Represents mutable sequences of bytes.
            
        * `memoryview`: Represents a memory view of an object, allowing access to its data in a memory-efficient way.
            
    8. **None Type:**
        
        * `None`: Represents the absence of a value. Often used as a default or placeholder value.
            
            ### **Exploring Data Types**
            
            In Python, you can use the `type()` function to determine the data type of a variable. Try creating variables with different data types and use `type()` to learn more about them.
            
            **Example:**
            
            ```python
            # Variables with different data types
            name = "John"
            age = 30
            pi = 3.14
            numbers = [1, 2, 3, 4, 5]
            coordinates = (10, 20)
            person = {"name": "John", "age": 30, "city": "New York"}
            
            # Print data types
            print(type(name))         # <class 'str'>
            print(type(age))          # <class 'int'>
            print(type(pi))           # <class 'float'>
            print(type(numbers))      # <class 'list'>
            print(type(coordinates))  # <class 'tuple'>
            print(type(person))       # <class 'dict'>
            ```
            
            ## Conclusion:
            
            Congratulations on taking your first steps into the incredible world of Python! This blog has introduced you to the wonders of Python, its installation on Windows and Ubuntu, and the fundamental concept of data types. With Python, you have a versatile and user-friendly programming language at your fingertips, ready to empower your projects and bring your ideas to life! 💻🔧