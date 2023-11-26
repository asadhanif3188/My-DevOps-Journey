# My DevOps Journey - Hard way 

------------------
## Outline

[Linux Basics](#-linux-basics)


------------------

## 1. Linux Basics

### 1.1 - Linux File System

- `/home`: home directories if all non-root users
- `/root`: home directory for root user 
- `/bin`: executables for most essential user commands  
- `/sbin`: essential system binaries, require superuser privilige 
- `/lib`: essential shared libraries that executables from /bin or /sbin use 
- `/usr`: this was user location before home, it contains binaries too. Third part apps resides in this directory.  
- `/usr/local`: programs installed here, will be available for all users on the computer.  
- `/opt`: third-party programs also resides here. those programs which NOT split its components are part of this directory. 
- `/boot`: contains files required for booting the system.  
- `/etc`: configuratoin for system-wide applications is stored. 
- `/dev`: locations of device filesm like webcam, keyboard, hard drive, etc.  
- `/var`: logs are placed in this directory 
- `/tmp`: temporary resources required for some process, kept here temporarily.  
- `/media`: contains subsirectories, where removable media devices inserted into the computer are mounted. 
- `/mnt`: temporary mount points 

### 1.2 - Basic Linux Commands 

**Basic Commands** 

- pwd
- ls 
    - ls -R
- tree 
- cd 
- man 
- clear 
- whoami 
- echo 
- date 
- cal 
- history 
- reboot 
- shutdown 
- alias 
- unalias 
- file

**Navigating the Files System**
- cd 
    - cd ~
    - cd -
- ls 
    - ls path/name
    - ls -a 
    - ls -l 
    - ls -t 
    - ls -S
    - ls -r 
    - ls -h

**Manipulating Files and Directories** 
- mkdir 
- rmdir 
- rm 
- cp 
    - cp -r 
- mv 
    - mv -i
    - mv -u

**Working with Text Files**
- touch
    - touch file1.txt file2.txt file3.txt
    - touch -t 202201011300
- cat 
    - cat file1.txt file2.txt file3.txt
    - cat -n file1.txt
    - cat file1.txt file2.txt > combined.txt
- less 
- more
- head
    - head -n 5 file.txt   
    - head -c 100 file.txt
    - head -f file.txt
    - head -v file.txt
- tail 
    - tail -n 5 file.txt   
    - tail -c 100 file.txt
    - tail -f file.txt
    - tail -v file.txt
- sort 
    - sort file.txt  (ascending order)
    - sort -r file.txt  (descending order)
    - sort -n file.txt  (sort numerically)
    - sort -f file.txt  (sort as case-insensitive)
    - sort -u file.txt  (remove any duplicate lines)
    - sort -k 2 file.txt  (sort lines based on second column)
- fold  (wrap lines to a specific width)
    - fold file.txt  (default 80 chars)
    - fold -w 60 file.txt
    - fold -w 8 -s -n file.txt
    - fold -w 40 file.txt > wrapped.txt 
- comm 
- wc 
    - wc -l myfile.txt  (line count)
    - wc -w myfile.txt  (word count)
    - wc -c myfile.txt  (chars count) (including white spaces)
    - wc -m myfile.txt  (chars count) (excluding white spaces)
    - wc myfile.txt  (count lines, words, chars)

- reverse search (ctrl + r)
- uname -a 
- lscpu 
- lsmem 
- adduser 
- 

### 1.3 - Package Manager 

**Software Package**

A compressed archive, containing all required files.

**Package Manager** 
- Installs or update existing softwares from a repository. 
- Ensure the integrity and authenticity of the package.
- Manages and resolves all required dependencies.

- List of few package managers:
    - APT 
    - SNAP 
    - YUM 

**Software Repositories**
- It is a storage location, containing different programs. 
- Package managers fetches the packages from these repositories. 
- Always update the package index before upgrading or installing new packages. 

- Update package index (sudo apt update)
    - Pulls the latest changes from APT repositories.
    - The APT package index is basically a database.
    - Holding records of available packages from the repositories. 

- `/etc/apt/sources.list` file contains all the repositories of different packages.  

**SNAP Package Manager**
- **Snap**: A snap is a bundle of an app and its dependencies. 
- **Snap Store** provides a place to upload snaps, and for users to brows and install the software.
- **Snapcraft** is the command and framework used to build and publish snaps. 

