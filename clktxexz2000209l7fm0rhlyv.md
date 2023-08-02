---
title: "Play with Linux Commands."
datePublished: Wed Aug 02 2023 16:12:16 GMT+0000 (Coordinated Universal Time)
cuid: clktxexz2000209l7fm0rhlyv
slug: play-with-linux-commands
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690992309163/57082483-31dc-4699-9229-93d2647f7096.jpeg
tags: linux, linux-for-beginners, linux-kernel, linux-basics, linux-commands

---

### **Command to view what's written inside a file?**

```plaintext
cat <filename>
```

The "cat" command shows the content written inside the file.

**Example:** Suppose, we have one file named "file1.txt" and inside this file "Hello DevOps" is written. So, to view what is written inside the file command should be like this

```plaintext
cat file1.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689569051328/4fbacbb8-5792-49e4-96b9-8b9fe4d099f8.png?auto=compress,format&format=webp align="left")

---

## Command to change the access permission of a file?

```plaintext
chmod 777 file1.txt
```

The Above command gives all permissions i.e. read, write and execute permissions to all ( Users, Groups and Others ).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689569297265/c9f031e1-072d-4149-aabd-21435458fa7d.png?auto=compress,format&format=webp align="left")

In the above screenshot, file1.txt has all the permission ( Read, Write, Execute )

Let's Understand how to provide permissions to a file in detail,

<table><tbody><tr><td colspan="1" rowspan="1" colwidth="256"><p><strong>Octal</strong></p></td><td colspan="1" rowspan="1"><p><strong>File mode</strong></p></td></tr><tr><td colspan="1" rowspan="1" colwidth="256"><p>1</p></td><td colspan="1" rowspan="1"><p>--x, executable permission</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="256"><p>2</p></td><td colspan="1" rowspan="1"><p>--w, write permission</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="256"><p>4</p></td><td colspan="1" rowspan="1"><p>--r, read permission</p></td></tr></tbody></table>

So, suppose you want to provide executable permission to groups, write permission to users and read permission to others, then the command should be like this,

executable permission to groups i.e. **octal "1"**

write permission to users i.e. **octal "2"**

read permission to others i.e. **octal "4"**

**command:** **chmod 124 file1.txt**

---

## Command to check which commands you have run till now.

```plaintext
history
```

history command shows us what all commands we have you till now.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689570598018/e469edb7-5966-4048-8d6f-a644fe6fbc8d.png?auto=compress,format&format=webp align="left")

---

## Command to remove Directory/Folder in Linux?

To remove an empty directory,

```plaintext
rmdir <directory-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689570697368/eb703af9-3367-4627-8eb0-d071eafa02ca.png?auto=compress,format&format=webp align="left")

To remove non-empty directories,

```plaintext
rm -r <directory-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689570836076/ca546c93-25fa-421f-9c6f-c5153e4aaf9e.png?auto=compress,format&format=webp align="left")

Here, -r means recursively.

---

## Command to create a fruits.txt file and to view the content?

To create a file "touch" command is used

```plaintext
touch <filename>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689571050923/5c0220bc-17ca-450b-b8c4-102407796186.png?auto=compress,format&format=webp align="left")

To view the content of a file, the "cat" command is used,

```plaintext
cat <filename>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689571098498/3ff222ab-42ff-4d03-a147-57afcb2fa087.png?auto=compress,format&format=webp align="left")

---

## Command to Add content in devops.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.

First create a file with "touch" command,

Example: touch devops.txt

Open devops.txt file with vim editor,

***vim, nano editors are used to add content to a file.***

Example: vim devops.txt

Press "i" to go into insert mode and add contents to the file,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689571376846/ad79cad0-e0e3-4645-b0d1-0479b93e167c.png?auto=compress,format&format=webp align="left")

and press "Esc + :wq" to save and exit from the file.

---

## Command to show only top three fruits from the file?

```plaintext
head -3 <filename>
```

In the above command, the "head" command gives us first part of a file.

\-3, --shows the top 3 lines of a file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689571851362/cc0859bd-cfd6-4231-9d58-edd47f300f53.png?auto=compress,format&format=webp align="left")

---

## Command to Show only the bottom three fruits from the file.

```plaintext
tail -3 <filename>
```

In the above command, the "tail" command gives us last part of a file.

\-3, --shows the bottom 3 lines of a file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689572109449/4cbe554e-b652-42a9-b827-fd1f76e79a4c.png?auto=compress,format&format=webp align="left")

---

## Command to create another file Colors.txt and to view the content.

```plaintext
touch <filename>
```

To see the content of a file,

```plaintext
cat <filename>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689572262960/b688f056-0f11-4627-a78c-27079e7c7d41.png?auto=compress,format&format=webp align="left")

---

## Command to add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.

Open colors.txt file with vim editor,

***vim, nano editors are used to add content to a file.***

Example: vim colors.txt

Press "i" to go into insert mode and add contents to the file,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689572416939/9f6ee065-bfba-4044-ae0d-1e327e266e17.png?auto=compress,format&format=webp align="left")

and press "Esc + :wq" to save and exit from the file.

## **Command to find the difference between fruits.txt and Colors.txt files.**

```plaintext
diff <file1> <file2>
```

> ***"diff" command is used to check difference between two files.***

Let's understand with the help of the below screenshot,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689572832787/bb7919fd-724e-4b5d-818c-bb35e9d9bbc0.png?auto=compress,format&format=webp align="left")

Here, in "devops.txt" file we have content,

* Apple
    
* red
    
* blue
    
* yellow
    
* green
    
* maroon
    
* and in "colors.txt" file we have,
    
* red
    
* blue
    
* yellow
    
* green
    
* maroon
    

> ***diff command shows the difference between two files***