---
title: "Linux🐧Shell Scripting! 🚀"
datePublished: Thu Aug 03 2023 18:57:20 GMT+0000 (Coordinated Universal Time)
cuid: clkvir2oh000909jo8eec14m0
slug: linuxshell-scripting
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691088015234/2ed3a39b-c09a-4cea-938c-08c175ab12f7.jpeg
tags: linux, script, linux-for-beginners, shell-script, trainwithshubham

---

## 🐚 What is Shell? 🤔

**A** shell is a special user program that provides an interface for the user to use operating system services. Shell accepts human-readable commands from users and converts them into something which the kernel can understand. It is a command language interpreter that executes commands read from input devices such as keyboards or from files. The shell gets started when the user logs in or start the terminal. 💻

## 🐧 What is Linux Shell Scripting?

**S**hell scripting is the art of writing scripts using a command-line shell (like Bash) to automate tasks and streamline workflows in the DevOps domain. It allows DevOps engineers to create powerful, reusable scripts that execute a series of commands, perform system operations, manage deployments, and more. Shell scripts act as a bridge between human-readable commands and machine-executable instructions, making complex tasks easily reproducible and automated.

### 📝 Example:

Let’s say you have a deployment process that involves pulling code from a Git repository, building the application, and deploying it to a production server. Instead of manually executing each step, <mark>a shell script can automate this process</mark>, ensuring consistency and efficiency in deployments. 🚀

### **🐚 Shell Scripting for DevOps:**

* 🔧 Shell scripting is a powerful tool for DevOps professionals that enables automation, efficiency, and consistency in various tasks.
    
* ⚙️ Shell scripts are written using scripting languages like Bash, Python, or PowerShell, and they allow for the execution of multiple commands in a sequence.
    
* 🚀 DevOps engineers utilize shell scripting to automate deployment processes, server configurations, and application management, saving time and reducing errors.
    
* 💻 Shell scripts can handle file manipulation, process control, system monitoring, and interactions with APIs, making them versatile for various DevOps tasks.
    
* 🔄 By leveraging shell scripting, DevOps practitioners can create repeatable and scalable workflows, improving collaboration and accelerating software delivery.
    

### `#!/bin/bash` **and** `#!/bin/sh` **Are they the same or different?**

`#!/bin/bash` and `#!/bin/sh` are known as shebangs or hashbangs. They are special constructs used in Unix-like operating systems to specify the interpreter for executing a script.

`#!/bin/bash` specifies that the script should be executed using the Bash shell, which is a popular and widely used Unix shell. Bash provides a rich set of features and extensions beyond what is defined by the POSIX standard for shell scripting.

On the other hand, `#!/bin/sh` specifies that the script should be executed using the default system shell, which is typically a POSIX-compliant shell. The actual shell associated with `/bin/sh` may vary depending on the operating system and its configuration. In many cases, `/bin/sh` is linked to, which means that using `#!/bin/sh` would effectively use Bash as the interpreter.

While Bash is more feature-rich and offers additional capabilities compared to a basic POSIX shell, scripts written using `#!/bin/sh` should generally adhere to the POSIX standard to ensure portability across different Unix-like systems. If you specifically require the additional features of Bash, using `#!/bin/bash` is appropriate.

In summary, you can use either `#!/bin/bash` or `#!/bin/sh` at the beginning of a script, depending on your needs. However, it's worth noting that some advanced Bash features may not be available when using `#!/bin/sh`.

> ***Note: Extension of shell script must be ".sh"***

Let's look at this basic example of shell script,

Steps:

1. Create a new file and open the file
    

```plaintext
vim script.sh
```

1. Enter the following code
    

### **Script Example: 📝**

```plaintext
#!/bin/bash
# A simple script to greet the user

# Prompt for user input
read -p "Enter your name: " name

# Print a personalized greeting
echo "Hello, $name! Welcome to the world of Linux shell scripting!"
```

### **🐚 Shell Script to Print Message:**

```plaintext
#!/bin/bash
echo "I will complete #90DaysOofDevOps challenge."
```

### **🐚 Shell Script to take user input, input from arguments, and print the variables:**

```plaintext
# Prompt for user input and print
#!/bin/bash
read -p "Enter your name: " name
echo "Hi $name, Welcome to the World of DevOps."

# Prompt for user input from argument and print
#!/bin/bash
echo "Hi $name, Welcome to the World of DevOps."
sh script.sh Aman
```

### **🐚 Shell Script with if-else conditions:**

```plaintext
#!/bin/bash
 # Initializing the variable
 a=20
 if [ $a -lt 10 ] 
then  
      # If variable less than 10    
      echo "a is less than 10" 
elif [ $a -lt 25 ] 
then  
      # If variable less than 25  
      echo "a is less than 25" 
else   
     # If variable is greater than 25   
     echo "a is greater than 25"  
fi
```

### Conclusion📝

**T**his blog discussed the process of creating powerful scripts that automate tasks, streamline workflows, and optimize system management. It covered topics such as user interactions, command-line arguments, and creating dynamic and interactive scripts to suit individual requirements. 🚀