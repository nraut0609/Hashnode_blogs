---
title: "Advanced Linux Shell Scripting for DevOps Engineers with User management."
datePublished: Thu Aug 03 2023 19:34:09 GMT+0000 (Coordinated Universal Time)
cuid: clkvk2eza00020ak3a8kednhr
slug: advanced-linux-shell-scripting-for-devops-engineers-with-user-management
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691091113711/d2f3883e-b2fe-4583-a195-0d9c71baad25.avif
tags: linux, bash, script, linux-for-beginners, linux-basics

---

### **Task 5 of #90daysofdevops**

### **Task :-**

<mark>Write a bash script </mark> [<mark>createDirectories.sh</mark>](http://createDirectories.sh) <mark> that when the script is executed with three given arguments (one is the directory name and second is the start number of directories and third is the end number of directories ) it creates a specified number of directories with a dynamic directory name.</mark>

Example 1: When the script is executed as

`./`[`createDirectories.sh`](http://createDirectories.sh) `day 1 90`

then it creates 90 directories as `day1 day2 day3 .... day90`

Example 2: When the script is executed as

`./`[`createDirectories.sh`](http://createDirectories.sh) `Movie 20 50` then it creates 50 directories as `Movie20 Movie21 Movie23 ...Movie50`

**Answer:-**

```plaintext
 #!/bin/bash
 for (( i=$2;i<=$3;i++))
 do
      mkdir $1:$i
 done
 ls
```

We just have to use 2 arguments while execution i.e.

`./`[`createDirectories.sh`](http://createDirectories.sh) `day 1 90`

`./`[`createDirectories.sh`](http://createDirectories.sh) `Movie 20 50`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673009600025/d59a2913-1e8a-4ec9-8a66-47e136b3099e.jpeg?auto=compress,format&format=webp align="left")

1. **Create a Script to back up all your work done till now.**
    
    ```plaintext
     #!/bin/bash
    
     src_dir=/home/ubuntu/*
     dest_dir=/home/ubuntu/recovery
    
     curr_timestamp=$(date "+%Y-%m-%d-%H-%M-%S")
    
     backup_file=$dest_dir/$curr_timestamp.tgz
    
     tar -cvzf $backup_file --absolute-names $src_dir
    
     echo "Backup is taken on $curr_timestamp"
     echo "Backup Completed successfully."
    ```
    
2. **About Cron and Crontab, to automate the backup Script**
    
    **Cron**
    
    Cron is a service/process which allows scheduling or automating a particular task at a predefined interval.
    
    **Crontab**
    
    Crontab is a job scheduling utility used to schedule a particular script /Linux command written in a file for a specific time, day or period. It is configured in `/etc/crontab`. `crond` is a daemon utilised to manage cronjob. Always used for regular tasks which helps in reducing human efforts & errors.
    
    **Syntax:** `crontab <option> <user>`
    
    where options are
    
    `-e`, `-u`, `-l`, `-r`
    
    To create a new cronjob for the root user, use the following command and enter the new cron entry in a text editor
    
    `crontab -e`
    
    To list out the crontab list, use this command
    
    `crontab -l`
    
    To create a cronjob for the particular user, use this command
    
    `crontab -u`
    
    To remove created cronjob, use this command
    
    `crontab -r`
    
    **Scheduling format** **:**
    
    `* * * * * user-name <script/command path>`
    
    1)Minute(0-59)
    
    2)Hour (0-23)
    
    3)Day of Month (1-31)
    
    4)Month (1-12) or (Jan, Feb, Mar,......., Dec)
    
    5)Week (0-7) or (Sun, Mon, Tue, Wed, Thu, Fri, Sat, Sun)
    
    where,
    
    `* means all/unknown`
    
    `- means Range`
    
    `, means list/separator`
    
    `/ means interval`
    
    **Example :**
    
    `17 6 * * * echo "This is my first cron job" > /home/ubuntu/first_cronjob.txt`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672986109436/ada7adb0-7975-4bdf-a789-15e71097f7ba.jpeg?auto=compress,format&format=webp align="left")
    
3. **About User Management**
    
    A user is an entity, in a Linux operating system, that can manipulate files and perform several other operations. Each user is assigned an id that is unique for each user in the operating system.
    
    id 0 is assigned to the root user and the id's 1 to 999 (both inclusive) are assigned to the system users hence the ids for local user begins from 1000 onwards. In a single directory, we can create 60,000 users.
    
    **Command to list all the users:**
    
    ```plaintext
     awk -F':' '{print $1}' /etc/passwd
    ```
    
    with the help of **the awk command**, we are printing the first column separated by “:”
    
    **Command to get the id of a user:**
    
    ```plaintext
     id username
    ```
    
    **Command to add a user:**
    
    ```plaintext
     sudo useradd username
    ```
    
    **Command to assign a password to a user:**
    
    ```plaintext
     passwd username
    ```
    
    **Command to access user configuration:**
    
    ```plaintext
     cat /etc/passwd
    ```
    
    **Command to change userid:**
    
    ```plaintext
     usermod -u new_id username
    ```
    
    **Command to modify the group id of a user:**
    
    ```plaintext
     usermod -g new_group_id username
    ```
    
    **Command to change login name for a user:**
    
    ```plaintext
     usermod -l new_login_name old_login_name
    ```
    
    **Command to change the home directory of a user:**
    
    ```plaintext
     usermod -d new_home_dir username
    ```
    
    **Command to delete a user:**
    
    ```plaintext
     userdel -r username
    ```
    
    **Note:** If a user is part of a group, then we have to remove the user from the group and then delete the user.
    
4. **Create 2 users and just display their Usernames**
    
    `sudo useradd Shawn`
    
    `sudo useradd Mendis`
    
    To display their usernames, the following command is used:
    
    `awk -F':' '{print $1}' /etc/passwd`
    
    Reference link: [**https://youtu.be/aolKiws4Joc**](https://youtu.be/aolKiws4Joc)
    
    > ***Thanks for reading.***
    > 
    > ***See you next time.***