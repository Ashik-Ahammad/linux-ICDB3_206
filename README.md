# Linux Fundamentals Assignment

This repository contains a script and corresponding output for basic Linux file system navigation, file and directory operations, permission changes, user management, and package installation.

## File System Navigation

1. **List the contents of the home directory:**
    ```sh
    ls ~
    ```
    *This command lists all files and directories in your home directory.*

2. **Change the current directory to `/var/log` and list its contents:**
    ```sh
    cd /var/log
    ls
    ```
    *Navigates to the `/var/log` directory and displays its contents.*

3. **Find and display the path to the bash executable:**
    ```sh
    which bash
    ```
    *Identifies the location of the `bash` executable.*

4. **Find the current shell:**
    ```sh
    echo $SHELL
    ```
    *Displays the current shell in use.*

## File and Directory Operations

1. **Create a directory named `linux_fundamentals` in your home directory:**
    ```sh
    mkdir ~/linux_fundamentals
    ```
    *Creates a new directory called `linux_fundamentals` in your home directory.*

2. **Inside `linux_fundamentals`, create a subdirectory named `scripts`:**
    ```sh
    mkdir ~/linux_fundamentals/scripts
    ```
    *Creates a `scripts` directory inside `linux_fundamentals`.*

3. **Create an empty file named `example.txt` inside `linux_fundamentals`:**
    ```sh
    touch ~/linux_fundamentals/example.txt
    ```
    *Creates an empty file named `example.txt`.*

4. **Copy `example.txt` to the `scripts` directory:**
    ```sh
    cp ~/linux_fundamentals/example.txt ~/linux_fundamentals/scripts/
    ```
    *Copies `example.txt` to the `scripts` directory.*

5. **Move `example.txt` from `linux_fundamentals` to `linux_fundamentals/backup`:**
    ```sh
    mkdir ~/linux_fundamentals/backup
    mv ~/linux_fundamentals/example.txt ~/linux_fundamentals/backup/
    ```
    *Creates a `backup` directory and moves `example.txt` into it.*

## Permissions

1. **Change the permissions of `example.txt` to read and write for the owner, and read-only for the group and others:**
    ```sh
    chmod 644 ~/linux_fundamentals/backup/example.txt
    ```
    *Sets the permissions of `example.txt` to read/write for the owner and read-only for others.*

2. **Verify the permission changes using `ls -l`:**
    ```sh
    ls -l ~/linux_fundamentals/backup/example.txt
    ```
    *Displays the permissions of `example.txt`.*

## File Modification

1. **Create a file named `example.txt` in your home directory:**
    ```sh
    touch ~/example.txt
    ```
    *Creates an empty file named `example.txt` in the home directory.*

2. **Change the owner of `example.txt` to a user named `student`:**
    ```sh
    sudo chown student ~/example.txt
    ```
    *Changes the ownership of `example.txt` to the user `student`.*

3. **Change the group of `example.txt` to a group named `students`:**
    ```sh
    sudo chown :students ~/example.txt
    ```
    *Changes the group ownership of `example.txt` to the group `students`.*

4. **Verify the changes using `ls -l`:**
    ```sh
    ls -l ~/example.txt
    ```
    *Displays the updated owner and group information of `example.txt`.*

## Ownership

1. **Create a directory named `project` in your home directory:**
    ```sh
    mkdir ~/project
    ```
    *Creates a new directory named `project`.*

2. **Create a file named `report.txt` inside the `project` directory:**
    ```sh
    touch ~/project/report.txt
    ```
    *Creates an empty file named `report.txt` in the `project` directory.*

3. **Set the permissions of `report.txt` to read and write for the owner, and read-only for the group and others:**
    ```sh
    chmod 644 ~/project/report.txt
    ```
    *Sets the permissions of `report.txt`.*

4. **Set the permissions of the `project` directory to read, write, and execute for the owner, and read and execute for the group and others:**
    ```sh
    chmod 755 ~/project
    ```
    *Sets the permissions of the `project` directory.*

5. **Verify the changes using `ls -l`:**
    ```sh
    ls -l ~/project/report.txt
    ls -ld ~/project
    ```
    *Displays the permissions of the `report.txt` file and the `project` directory.*

## User Add/Modify

1. **Create a new user named `developer`:**
    ```sh
    sudo useradd developer
    ```
    *Creates a new user named `developer`.*

2. **Set the home directory of the user `developer` to `/home/developer_home`:**
    ```sh
    sudo usermod -d /home/developer_home developer
    ```
    *Changes the home directory of the user `developer`.*

3. **Assign the shell `/bin/sh` to the user `developer`:**
    ```sh
    sudo usermod -s /bin/sh developer
    ```
    *Sets the login shell for `developer` to `/bin/sh`.*

4. **Verify the new user's information:**
    ```sh
    getent passwd developer
    ```
    *Displays detailed information about the `developer` user.*

5. **Change the username of the user `developer` to `devuser`:**
    ```sh
    sudo usermod -l devuser developer
    ```
    *Changes the username from `developer` to `devuser`.*

6. **Add `devuser` to a group named `devgroup`:**
    ```sh
    sudo groupadd devgroup
    sudo usermod -aG devgroup devuser
    ```
    *Creates a new group called `devgroup` and adds `devuser` to it.*

7. **Set the password of `devuser` to `devpass`:**
    ```sh
    sudo passwd devuser
    ```
    *Sets the password for `devuser`.*

8. **Verify the changes made to the user:**
    ```sh
    getent passwd devuser
    id devuser
    ```
    *Displays the information and group memberships of `devuser`.*

## Hard/Soft Link

1. **Create a file named `original.txt` in your home directory:**
    ```sh
    touch ~/original.txt
    ```
    *Creates an empty file named `original.txt`.*

2. **Create a symbolic link named `softlink.txt` pointing to `original.txt`:**
    ```sh
    ln -s ~/original.txt ~/softlink.txt
    ```
    *Creates a symbolic link `softlink.txt` pointing to `original.txt`.*

3. **Verify the symbolic link:**
    ```sh
    ls -l ~/softlink.txt
    ```
    *Displays information about the symbolic link.*

4. **Delete the original file `original.txt` and check the status of the symbolic link:**
    ```sh
    rm ~/original.txt
    ls -l ~/softlink.txt
    ```
    *Deletes `original.txt` and checks the status of `softlink.txt`.*

5. **Create a file named `datafile.txt` in your home directory:**
    ```sh
    touch ~/datafile.txt
    ```
    *Creates an empty file named `datafile.txt`.*

6. **Create a hard link named `hardlink.txt` pointing to `datafile.txt`:**
    ```sh
    ln ~/datafile.txt ~/hardlink.txt
    ```
    *Creates a hard link `hardlink.txt` pointing to `datafile.txt`.*

7. **Verify the hard link:**
    ```sh
    ls -l ~/datafile.txt ~/hardlink.txt
    ```
    *Displays information about both the original file and the hard link.*

8. **Check the inode of both `datafile.txt` and `hardlink.txt`:**
    ```sh
    ls -i ~/datafile.txt ~/hardlink.txt
    ```
    *Displays the inode numbers for both files.*

9. **Delete the original file `datafile.txt` and observe the status of the hard link:**
    ```sh
    rm ~/datafile.txt
    ls -l ~/hardlink.txt
    ```
    *Deletes `datafile.txt` and checks the status of `hardlink.txt`.*

10. **Find all `.txt` files in your home directory:**
    ```sh
    find ~ -name "*.txt"
    ```
    *Searches for all `.txt` files in your home directory.*

## Package Installation

1. **Update repo cache using `apt`/`apt-get`:**
    ```sh
    sudo apt update
    ```
    *Updates the package list.*

2. **Install a package named `tree`:**
    ```sh
    sudo apt install tree
    ```
    *Installs the `tree` package.*

3. **Install gcloud CLI tool using apt:**
    ```sh
    sudo apt-get install apt-transport-https ca-certificates gnupg curl
    echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] http://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
    curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key --keyring /usr/share/keyrings/cloud.google.gpg add -
    sudo apt-get update && sudo apt-get install google-cloud-cli
