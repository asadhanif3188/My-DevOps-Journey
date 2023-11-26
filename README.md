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
- tac   (cat in reverse) 
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
- uniq  (used to remove adjacent duplicate lines)
- cut   (used to extract specific columns from lines of a file or input) 
- split     (split a file into smaller parts)
- sed   (stream editor) (used to find and replace strings)
    - sed 's/old_txt/new_txt/g' file.txt
    - sed 's/old_txt/new_txt/' file.txt
    - sed -i 's/old_txt/new_txt/g' file.txt
    - sed '/pattern/d' file.txt   (delete the line matching pattern)
    - sed '3a\New line to append' file.txt   (append the text after line 3)
    - sed '3i\New line to insert' file.txt   (insert the text before line 3)
    - sed '2d' file.txt    (delete 2nd line)
- grep
    - grep -i "search_string" file.txt  (case insensitive)
    - grep -c "search_string" file.txt  (count number of lines)
    - grep -o "search_string" file.txt  (print only matched string)
    - grep -n "search_string" file.txt  (print line number too)
- find 

**Misc. Commands**
- reverse search (ctrl + r)
- uname -a 
- lscpu 
- lsmem 
- adduser 
- 

**Redirects and Pipes**
- 1>
- 2>
- 1>>
- 2>> 
- sort file.txt > sorted.txt 2> error.txt
- sort file.txt > sorted.txt 2>&1
- | (pipe)
    - cat file.txt | grep Apple 
    - cat file.txt | grep -v a | sort -r    (get only lines that do not contain char 'a') 

**Compression**
- gzip  (compress)
- gunzip  (decompress)
- bzip2  (compress)
- bunzip2  (decompress)

**Archive**
- tar
    - tar -cf test.tar file1 file2   (create tar with specified name)
    - tar -tf test.tar  (see contents of tar file)
    - tar -xf test.tar  (extract the contents of tarball) 
    - tar -czf test.tar.gz file1 file2  (compress the file with gzip) 
    - tar -cjf test.tar.gz2 (compress the file with bzip2)
    - tar -cjpf test.tar.gz2 (compress the file with bzip2 and preserve the permissions)
- zip 
    - zip -r test.zip dir_name (recursively zip a directory)
- unzip  (extract files into the current directory)

**Accounts and Groups**
- There four important files related to user accounts and groups:
    - `/etc/passw`
    - `/etc/shadow`
    - `/etc/group`
    - `/etc/gshadow`
- useradd
- adduser
- userdel
- deluser
- usermod 
- passwd
- sudo usermod --lock username   (lock/disable user)
- sudo passwd -l username   (lock/disable user)
- sudo usermod --unlock username   (unlock/enable user)
- sudo passwd -u username   (unlock/enable user)
- groupadd
- addgroup 
- groupdel
- delgroup
- groupmod 
- sudo usermod -aG groupname username   (Adding User to Group)
- sudo gpasswd -a username groupname   (Adding User to Group)
- sudo adduser username groupname   (Adding User to Group)
- sudo useradd -G groupname username   (Adding User to Group)
- sudo usermod -G "" username  (removes the user from all supplementary groups)
- sudo gpasswd -d username groupname   (removes the user from the specified group)
- sudo deluser username groupname  (removes the user from the specified group while removing the user)
- sudo userdel -G groupname username  (removes the user from the specified group while removing the user)

**Ownership and Permissions**
- sudo chown ali file.txt  (user only)
- sudo chown :dev-team file.txt  (group only)
- sudo chown ali:dev-team file.txt  (both)
- sudo chown -R ali file.txt  (recursive for sub-dirs)
- sudo chmod u+r file1
- sudo chmod u+rw file1
- sudo chmod u+rwx file1
- sudo chmod u-r file1
- sudo chmod u-rw file1
- sudo chmod u-rwx file1
- sudo chmod g+r file1
- sudo chmod g+rw file1
- sudo chmod g+rwx file1
- sudo chmod g-r file1
- sudo chmod g-rw file1
- sudo chmod g-rwx file1
- sudo chmod a+r file1
- sudo chmod a+rw file1
- sudo chmod a+rwx file1
- sudo chmod a-r file1
- sudo chmod a-rw file1
- sudo chmod a-rwx file1
- sudo chmod 777 file1
- sudo chmod 555 file1
- sudo chmod 660 file1
- sudo chmod 750 file1



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

### 1.4 - Secure Shell (SSH) 
- Secure Shell (SSH) is a network protocol that provides a secure way to access a remote machine (server) over the Internet. 
- It provides encrypted data communication. 
- OpenSSH is a tool/utility/library used to perform remote login.

**Ways to Authentication**
1. Username & Password
2. SSH Key Pair 

**SSH Config File**
- OpenSSH allows us to set up a per-user configuration file.
- Where we can store different SSH options for each remote machine we connect to.
- OpenSSH client-side configuration file is placed at `~/.ssh/config`.
- This file must be readable and writable only by the user and not accessible by others.
    - `sudo chmod 600 ~/.ssh/config`

**SSH Config File Example**
```
Host my-website.com
    HostName <ip-address-of-remote-server>
    User <username>
    IdentityFile ~/.ssh/id_rsa
```

### 1.5 - Bash Scripting 

**Shell:**
- The program that interprets and executes the various commands that we type in the terminal.
- Translates our command that the OS Kernel can understand. 

**Different Shell Implementations**
- `sh`: Bourne Shell, `/bin/sh`
- `bash`: Bourne again Shell, `/bin/bash`
    - improved version of sh
    - default shell program for most UNIX like systems 
- `zsh`: Z shell 

**Configure a server**

Create a file using nano or vim, `setup.sh`:

```
#!/bin/bash

echo "Setup and configure server..."

file_name=config.yaml

config_dir=$1

if [ -d "$config_dir" ]
then
        echo "Reading config directory contents.." 
        config_files=$(ls $config_dir)
else 
        echo "Config dir not found.. creating one"
        mkdir $config_dir
        touch "$config_dir/file.txt"
fi

echo "Using file $file_name to configure k8s."

echo "Here are all configuration files: $config_files"

user_group=$2
echo ""

if [ $user_group == "asad" ]
then 
  echo "$user_group: Configure the server"
elif [ $user_group == "admin" ]
then 
  echo "$user_group: you can also configure the server."
else
  echo "No permissions to configure the server"
fi
```

Run the script as:
```
./setup.sh dir-name asad
```

**Reading input**

```
#!/bin/bash

echo "Reading user input..."

read -p "Please enter your password: " user_passwd 

echo "You have entered $user_passwd"
```

**Parameters with Loop**

```
#!/bin/bash
echo "All params: $*"
echo "Number of params: $#"

for param in $*
do 

  if [ -d $param ]
  then 
    echo "Executing scripts in the dir.."
    ls -l $param
  fi

echo $param
done

sum=0
while  true
do 
  read -p "enter a score " score
  if [ $score == "q" ] 
  then 
   break
  fi
  sum=$(($sum+$score))
  echo "total score $sum"
done
```

