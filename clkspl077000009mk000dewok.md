---
title: "Introduction to Linux  &
Basics Commands."
datePublished: Tue Aug 01 2023 19:45:16 GMT+0000 (Coordinated Universal Time)
cuid: clkspl077000009mk000dewok
slug: introduction-to-linux-basics-commands
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690992904610/2783179a-6d23-4398-b1f1-39655a97b280.jpeg
tags: linux, linux-for-beginners, linux-basics, linux-commands, 90daysofdevops

---

## History of Linux🐧

🐧 Linux is a free and open-source software operating system from the Unix family.

👨‍💻 It was developed by Linus Torvalds, a student at the University of Helsinki, in September 1991.

📩 He posted the first code of Linux 0.01 on the Minix newsgroup on September 17, 1991.

💻 Due to its popularity, he continued to develop new code and released the first official version of Linux, version 0.02 on October 5, 1991.

🚀 Today, Linux is one of the most popular operating systems.

💪 90% of the fastest supercomputers run on Linux variants, including the top 10.

### **Basic Concept of Linux Programming**

* 🐧 Linux is an open-source operating system kernel that is highly adaptable
    
* 💻 Widely used for server-side applications and powers significant digital infrastructures
    
* 🌎 Has evolved into a culture and ecosystem of its own.
    
* 💡 Linux programming requires knowledge of C programming language and an understanding of its potential uses.
    

### **🏢🐧 Linux Architecture: Building Blocks of the OS! 🧱**

1. 📲 **Application** 📲- Applications in the Linux architecture are software programs that run on top of the operating system and interact with its components.
    
2. 🐚 **Shell 🐚-** The shell is like the command center of our building. It provides a command-line interface where you can interact with the system using text commands.
    
3. **⚙️ Kernel ⚙️-** The kernel is the core of our building, providing essential services and managing resources. It acts as a bridge between the hardware and software layers, ensuring smooth communication and coordination.
    
4. **🖥️ Hardware** 🖥️-The hardware represents the physical infrastructure of our building. It includes your computer's components like the processor, memory, hard drive, graphics card, and other peripherals.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690917811643/d82b2271-382e-4842-8105-4c9434999b26.png align="center")
    

### 🐧📁Linux File System Hierarchy

* In Linux everything is represented as a file including a hardware program, the files are stored in a directory, and every directory contains a file with a tree structure🌳. That is called File System Hierarchy.
    
* 🔝Linux uses a single-rooted, inverted tree-like structure.
    
* Root Directory represents with / (forward slash) It is a top-level directory in Linux.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690916210006/608bb1b5-b669-4098-8afd-c9c37ce42eba.png align="center")

* 📂 The file system hierarchy starts from the root directory ("/"), which is the primary hierarchy root and the root directory of the entire system.
    
* 🔐Only the root user has write access to the root directory.
    
* 🏠 The root directory is not the same as the user's home directory ("/home").
    
* 📦 Essential command binaries are located in the "/bin" directory.
    
* 🔧 Common Linux commands used in single-user mode are found in "/bin". 🔌
    
* The "/boot" directory contains boot loader files like kernels and initrd.
    
* 🖥️ Essential device files are stored in the "/dev" directory.
    
* 📝 System-wide configuration files are located in the "/etc" directory.
    
* 🏠 Users' home directories are stored in "/home".
    
* 📚 Libraries essential for binaries in "/bin" and "/sbin" are found in the "/lib" directory.
    
* 💿 Mount points for removable media are located in the "/media" directory.
    

## Linux🐧 Basic 👨‍💻 Commands

### 📂 **Navigating the File System** 📂

* `ls`: List files and directories in the current location.
    
    ```plaintext
      ls [options] [directory]
    ```
    
* `cd`: Change the directory to navigate through different folders.
    
    ```plaintext
      cd [directory]
    ```
    
* `pwd`: Print the current working directory.
    
    ```plaintext
      pwd
    ```
    

### 📝 **Working with Files and Directories** 📝

* `mkdir`: Create a new directory.
    
    ```plaintext
      mkdir [directory]
    ```
    
* `touch`: Create a new empty file.
    
    ```plaintext
      touch [filename]
    ```
    
* `cp`: Copy files and directories.
    
    ```plaintext
      cp [options] [source] [destination]
    ```
    
* `mv`: Move or rename files and directories.
    
    ```plaintext
      mv [options] [source] [destination]
    ```
    
* `rm`: Remove files and directories.
    
    ```plaintext
      rm [options] [file/directory]
    ```
    
    ### 🔍 **File and Text Manipulation 🔍**
    
* `cat`: Display the content of a file.
    
    ```plaintext
      cat [filename]
    ```
    
* `head`: Display the first few lines of a file.
    
    ```plaintext
      Syntax: head [OPTIONS] [FILE]
    ```
    
    **EXAMPLE:**
    
    ```plaintext
      head -n 10 myfile.txt
    ```
    
    **In the example above,** `-n 10` **specifies that you want to display the first 10 lines of the file.**
    
* `tail`: Display the last few lines of a file.
    
    ```plaintext
      tail [options] [file]
    ```
    
    EXAMPLE:
    
    ```plaintext
      tail -n 10 file.txt
    ```
    
    **In the example above, displays the last 10 lines of the file "file.txt"**
    

### **🔧 System Administration 🔧**

* `sudo`: Execute a command with administrative privileges.
    
    ```plaintext
      sudo [command]
    ```
    
* `apt-get` (for Debian-based distros) or `dnf` (for Fedora-based distros): Package management commands for installing, updating, and removing software.
    
* `sudo apt update`: Used to update the package index files to get the latest list of available packages in the repositories.
    
    ```plaintext
      sudo apt update
    ```
    
* `sudo apt upgrade`: Used to install available upgrades of all packages currently installed on the system from the sources configured via sources.
    
    ```plaintext
      sudo apt upgrade
    ```
    

### 🔒 User and Permission Management:

* `whoami`: Print the current username.
    
    ```plaintext
      whoami
    ```
    
* `passwd`: Change the password for the current user.
    
    ```plaintext
      passwd
    ```
    
* `useradd`: Add a new user.
    
    ```plaintext
      useradd [options] username
    ```
    
* What is the Linux command to check your present working directory?
    
    ```plaintext
      pwd
    ```
    
* What is the Linux command to List all the files or directories including hidden files?
    
    ```plaintext
      ls -a
    ```
    
* What is the Linux command to create a nested directory A/B/C/D/E?
    
    ```plaintext
      mkdir -p A/B/C/D/E
    ```
    

### 👨‍💻**Benefits of Linux** 🐧

* **🆓 Cost-effective:** Linux is free and open-source, saving you money on licensing fees.
    
* **🔒 Secure:** Linux has a robust security framework, making it less vulnerable to viruses and malware.
    
* **💪 Customizable:** Linux allows users to personalize their operating system according to their preferences and needs.
    
* **🚀 Performance:** Linux is known for its efficiency and performance, making it ideal for resource-intensive tasks.
    
* **🌍 Compatibility:** Linux supports a wide range of hardware architectures and has extensive software compatibility.
    
* **🔄 Stability:** Linux is renowned for its stability and reliability, offering long uptimes and minimal crashes.
    
* **👥 Community Support:** Linux has a vibrant community of users and developers who provide support, guidance, and regular updates.
    
* **📚 Open-source Software:** Linux provides access to a vast repository of free and open-source software, fostering innovation and collaboration.
    
* **🌟 Scalability:** Linux scales seamlessly from small devices to large servers, making it suitable for diverse environments.
    
* **💻 Versatility:** Linux offers a range of distributions and desktop environments, catering to various user preferences and requirements.
    
* Embrace the power of Linux and unlock a world of flexibility, security, and customization! 🐧✨🔓
    
    ### **🌟 Conclusion:**
    
    Congratulations! 🎉 You've taken your first steps into the fascinating world of Linux. We hope this blog has given you a taste of what Linux is all about. Remember, Linux is a vast and versatile operating system, with endless possibilities waiting for you to explore! 🚀 Embrace the penguin power and have fun with your Linux journey! 🐧💪
    
    🔍 Did you find this blog helpful? Let us know in the comments below! 👇 And if you have any questions or need further assistance, we're here to help! 🤗
    
    Happy Linux-ing! 💻✨