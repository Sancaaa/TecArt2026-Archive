## Mastering Linux in a Day

This documentation is prepared by the Cyber Security Division for the Garasi Cyber: Jago Linux 1 Hari workshop. This guide covers everything from environment setup to core Linux services.

## What is Linux?
Linux is a free and open-source operating system kernel developed by Linus Torvalds. It serves as the core that manages system resources and hardware communication. Being community-driven ensures it stays secure and up-to-date.

## Why Learn Linux?
 Industry Standard: Powers over 90% of the world's cloud infrastructure.\
 Cyber Security: Most security auditing tools (like Kali Linux) are built on Linux.\
 Full Control: Allows for deep system customization and automation via scripting.

---

## Environment Setup (WSL vs VM)

Choose the method that best fits your hardware:

### 1. Windows Subsystem for Linux (WSL)
Best for: Users with limited RAM (4GB/8GB) or those who want seamless integration with Windows
 - Open Windows PowerShell as Administrator
 - Run the command: `wsl --install`.
 - Wait for the process to finish, then restart your PC.
 Important: Set your username and password, and remember them!

### 2. VM VirtualBox
Best for: Users who want total isolation ("a computer inside a computer") or for future academic use.
 - Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
 - Also Download TecArt Ubuntu VM [TecartUbuntuVM](https://drive.google.com/file/d/1NbL9IRPFozQm49CLPITLgDRcp4d4ka7g/view?usp=sharing).
 - Extract the provided Ubuntu VM file.
 - In VirtualBox, click Import and select the extracted file.
 - Credentials: \
     Username: `tecart`\
     Password: `tecart`\
 Launch the VM and log in.

### 3. Connection Testing
Once your Linux is running, ensure you have internet access:\
 Run: `ping google.com`\
 Ensure you get a reply. Press `CTRL+C` to stop the test.

---

## Preparations: Dummy File
Before starting the workshop, download the required dummy file:
```bash
wget [https://gist.githubusercontent.com/agusdarma-lab/abe7212826f8f96fb203cef828f1ac5c/raw/78f706ba1396a76527742b0076044dc459156479/dummy.txt](https://gist.githubusercontent.com/agusdarma-lab/abe7212826f8f96fb203cef828f1ac5c/raw/78f706ba1396a76527742b0076044dc459156479/dummy.txt)
```
Verify the file exists by typing ls.

---

## Linux Basic Commands (In-Depth)
- ```pwd```: Print Working Directory
- ```ls```: List. Lists files and directories in the current folder.
- ```cd```: Change Directory. Used to navigate between folders (e.g., cd .. to go up or cd folder_name).
- ```mkdir```: Make Directory. Creates a new folder.
- ```rm```: Remove. Deletes files or directories.
- ```cp```: Copy. Copies files or directories from a source to a destination.
- ```mv```: Move/Rename. Moves files or renames them.
- ```cat```: Concatenate. Displays the entire content of a file on the terminal.
- ```grep```: Search. Finds specific text patterns within files or command outputs.
- ```sudo```: SuperUser Do. Executes commands with root (administrative) privileges, also known as "Linux's God" mode.

---

## Linux Permissions
Linux manages security through a robust permission system for the User, Group, and Others.\
Permission Values:
- Read (r): Value = 4.
- Write (w): Value = 2.
- Execute (x): Value = 1.
  
 Example: chmod 755 file.txt
- Owner (7): 4+2+1 => rwx (Full control).
- Group (5): 4+1 => r-x (Read and Execute).
- Others (5): 4+1 => r-x (Read and Execute).

---

## Secure Shell (SSH)
SSH is used to manage remote servers via an encrypted connection.

### Installation (OpenSSH)
To install the SSH server on your Linux machine, run:

```sudo apt update```\
```sudo apt install openssh-server```

### Usage
- Check Status: ```sudo systemctl status ssh```
- Connect: ```ssh username@server_ip```

---

## Web Server (Apache2)
A Web Server processes HTTP requests to serve website content.

### 1. Installation
Install Apache2 using the following command:

```sudo apt update```\
```sudo apt install apache2```

### 2. Configuring HTML File
The default web directory is /var/www/html. You can edit the main page using nano:

```sudo nano /var/www/html/index.html```

### 3. Simple HTML Example
Replace the content of index.html with this code:
```
<!DOCTYPE html>
<html>
<head>
    <title>TecArt Workshop</title>
</head>
<body>
    <h1>Hello from Linux!</h1>
    <p>This server is running on Apache2.</p>
</body>
</html>
```
### 4. Testing the Web Server
To view your website, open a web browser and type your Linux IP address in the address bar:

- Check your IP: ```ip a```
- In Browser: ```http://[your_ip_address]```
