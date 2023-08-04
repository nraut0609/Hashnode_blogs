---
title: "🧰 What is a package manager in Linux?"
datePublished: Fri Aug 04 2023 18:24:52 GMT+0000 (Coordinated Universal Time)
cuid: clkwx16mt000109jn904vdwj8
slug: what-is-a-package-manager-in-linux
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691173167492/ae9c467b-e326-433f-83b9-e8cfc3d7a272.png
tags: linux, packages, installation, linux-for-beginners, linux-basics

---

**A** 📦package manager is a tool that is used to install, upgrade, manage, and remove packages. It is responsible to manage dependencies and to track all installed packages.

**🏭 Repositories**: Package managers have access to vast collections of software called repositories, like online stores filled with free and open-source software ready for installation.

**🔍 Searching:** You can search for software packages by name or keywords using the package manager, just like searching for products in an online marketplace.

**➕ Installation**: Once you find the software you want, simply ask the package manager to install it. It takes care of all the complex steps, such as downloading, verifying, and setting up the software.

**🔄 Updates:** The package manager also updates your software by regularly checking for updates and notifying you when new versions are available. Upgrading is as easy as clicking a button.

**❌ Removal:** If you no longer need a software package, you can ask the package manager to remove it, which will clean up all related files for you.

**📋 Dependencies:** Some software relies on other software to work correctly. Package managers handle these dependencies automatically, ensuring everything works smoothly together.

**🔐 Security:** Package managers verify the authenticity of the software you install, reducing the risk of malicious or compromised packages.

**🌟 Convenience:** With a package manager, you save time and effort. No need to visit different websites, download installers, or worry about updates. Everything is streamlined and managed in one place. 😊

### **📦 What is a package?**

In Linux, a package is a software distribution format that contains all the necessary files and information 📃 required to install and manage a specific piece of software. Packages typically include the executable binaries 💾, libraries 📚, configuration files 📝, and documentation 📄 needed to run the software on a Linux system 🐧.

* dpkg (Debian Package Manager)
    
* APT (Advanced Package Tool)
    
* rpm (RedHat Package Manager)
    
* yum (Yellowdog Update Modified)
    
* dnf (Dandified Yum)
    
* zypper
    
* flatpak
    
* pacman
    

### **APT (Advanced Package Tool):**

APT is widely used in Debian-based distributions like Ubuntu and is known for its user-friendly command-line interface. This package manager simplifies the process of interacting with the package management system, making it easier for users to perform various operations. 🛠️

With APT, you can effortlessly install, update, and remove packages using simple commands:

* To install a package: `sudo apt-get install package_name`
    
* To update packages: `sudo apt-get update` followed by `sudo apt-get upgrade`
    
* To remove a package: `sudo apt-get remove package_name`
    

### **YUM (Yellowdog Updater Modified):**

YUM is commonly used in Red Hat-based distributions like CentOS and Fedora. Similar to APT, YUM provides a command-line interface for managing packages, making it convenient for users to handle software installations. 🛠️

* To install a package: `sudo yum install package_name`
    
* To update packages: `sudo yum update` followed by `sudo apt-get upgrade`
    

To remove a package: `sudo yum remove package_name`

### 🎁 **RPM (Red Hat Package Manager)**

RPM is like a well-known 🎁 gift box manager, the default package manager for Red Hat-based systems like Fedora, CentOS, and RHEL. Here's how you use it:

* **Install the Package**: `sudo apt install rpm` 🚀📦 (Unpacking the RPM gift!)
    
    ### **🔍 Understanding systemctl and systemd**
    
    **systemd:** `systemd` is a system and service manager for Linux. It serves as the init system, replacing SysVinit in modern distributions due to enhanced features and improved performance.
    
    It manages system initialization, processes, startup, shutdown, and resource utilization efficiently. One key advantage is starting services in parallel, reducing boot times. It provides socket activation for on-demand service start.
    
    Commonly used commands: `systemctl` and `journalctl`.
    
    **systemctl:** `Systemctl` is a command-line utility used to manage system services in Linux distributions that adopt the `systemd init` system. `Systemd` is a system and service manager that provides advanced features such as process management, logging, and service dependencies.
    
    **Commands:**
    
    * 🔍 `sudo systemctl start service_name`
        
    * 🛠️ `sudo systemctl stop service_name`
        
    * 🔄 `sudo systemctl restart service_name`
        
    * 🔔 `sudo systemctl enable service_name`
        
    * 🔕 `sudo systemctl disable service_name`
        
        ## **🐳 Docker Installation using Package Managers 📦**
        
        Docker, the containerization marvel, allows us to encapsulate applications and dependencies in lightweight containers. Let's install Docker on both Ubuntu and CentOS using their respective package managers.
        
        📌 **Ubuntu Installation (using apt)**:
        
        * Open your terminal and update package lists:
            
            ```plaintext
              codesudo apt update
            ```
            
        * Install Docker using apt:
            
            ```plaintext
              codesudo apt install docker.io
            ```
            
        * Verify Docker installation:
            
            ```plaintext
              codedocker --version
            ```
            
        
        📌 **CentOS Installation (using yum)**:
        
        * Open your terminal and update package lists:
            
            ```plaintext
              codesudo yum update
            ```
            
        * Install Docker using yum:
            
            ```plaintext
              codesudo yum install docker
            ```
            
        * Start Docker service:
            
            ```plaintext
              codesudo systemctl start docker
            ```
            
        * Enable Docker to start on boot:
            
            ```plaintext
              sudo systemctl enable docker
            ```
            
        * Verify Docker installation:
            
            ```plaintext
              codedocker --version
            ```
            
        
        ## **🏗️ Jenkins Installation using Package Managers 📦**
        
        Jenkins, the automation powerhouse, empowers us to build, test, and deploy projects. Let's install Jenkins on both Ubuntu and CentOS using their respective package managers.
        
        📌 **Ubuntu Installation (using apt)**:
        
        * Add Jenkins repository key:
            
            ```plaintext
              wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
            ```
            
        * Add Jenkins repository to sources list:
            
            ```plaintext
              sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
            ```
            
        * Update package lists:
            
            ```plaintext
              sudo apt update
            ```
            
        * Install Jenkins using apt:
            
            ```plaintext
              sudo apt install jenkins
            ```
            
        * Start Jenkins service:
            
            ```plaintext
              sudo systemctl start jenkins
            ```
            
        * Enable Jenkins to start on boot:
            
            ```plaintext
              sudo systemctl enable jenkins
            ```
            
        
        📌 **CentOS Installation (using yum)**:
        
        * Add Jenkins repository to yum repository list:
            
            ```plaintext
              sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins.io/redhat-stable/jenkins.repo
            ```
            
        * Import Jenkins repository key:
            
            ```plaintext
              sudo rpm --import http://pkg.jenkins.io/redhat-stable/jenkins.io.key
            ```
            
        * Install Jenkins using yum:
            
            ```plaintext
              sudo yum install jenkins
            ```
            
        * Start Jenkins service:
            
            ```plaintext
              sudo systemctl start jenkins
            ```
            
        * Enable Jenkins to start on boot:
            
            ```plaintext
                  sudo systemctl enable jenkins
            ```
            
            These commands can be useful for managing system services on Linux systems, including starting, stopping, and monitoring services as well as configuring which services start at boot.
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691173359276/e6ba460e-4f03-4eab-a4f4-6a2faaa1f184.webp align="center")