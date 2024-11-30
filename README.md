# Linux Fundamentals Assignment

This repository contains a script and corresponding output for basic Linux file system navigation, file and directory operations, permission changes, user management, and package installation.

## File System Navigation

1. **List the contents of the home directory:**
    ```sh
    ls ~
    ```
    *This command lists all files and directories in home directory.*
    ![image](https://github.com/user-attachments/assets/b198e5c7-2845-48c3-b4d6-a78bd88b0244)


2. **Change the current directory to `/var/log` and list its contents:**
    ```sh
    cd /var/log
    ls
    ```
    *Navigates to the `/var/log` directory and displays its contents.*
    ![image](https://github.com/user-attachments/assets/1352aff4-d7ee-418b-be42-42ea823b5be9)


3. **Find and display the path to the bash executable:**
    ```sh
    which bash
    ```
    *Identifies the location of the `bash` executable.*
   ![image](https://github.com/user-attachments/assets/adc68da9-250b-4437-80c6-a94c7c10dcd5)


4. **Find the current shell:**
    ```sh
    echo $SHELL
    ```
    *Displays the current shell in use.*
   ![image](https://github.com/user-attachments/assets/f3534f6d-8e5f-486a-878e-ec430622a35e)


## File and Directory Operations

1. **Create a directory named `linux_fundamentals` in  home directory:**
    ```sh
    mkdir ~/linux_fundamentals
    ```
    *Creates a new directory called `linux_fundamentals` in  home directory.*
   ![image](https://github.com/user-attachments/assets/55b4a3b7-a598-4fc3-a3c5-aade6a3db719)


2. **Inside `linux_fundamentals`, create a subdirectory named `scripts`:**
    ```sh
    mkdir ~/linux_fundamentals/scripts
    ```
    *Creates a `scripts` directory inside `linux_fundamentals`.*
   ![image](https://github.com/user-attachments/assets/8e0d7807-24e9-4599-8e93-720edcfde92e)


3. **Create an empty file named `example.txt` inside `linux_fundamentals`:**
    ```sh
    touch ~/linux_fundamentals/example.txt
    ```
    *Creates an empty file named `example.txt`.*
   ![image](https://github.com/user-attachments/assets/82182494-fb9a-41a3-90b3-441f79a8f482)


4. **Copy `example.txt` to the `scripts` directory:**
    ```sh
    cp ~/linux_fundamentals/example.txt ~/linux_fundamentals/scripts/
    ```
    *Copies `example.txt` to the `scripts` directory.*
   ![image](https://github.com/user-attachments/assets/8a7e1614-ad30-459a-a012-b081b0ae5153)


5. **Move `example.txt` from `linux_fundamentals` to `linux_fundamentals/backup`:**
    ```sh
    mkdir ~/linux_fundamentals/backup
    mv ~/linux_fundamentals/example.txt ~/linux_fundamentals/backup/
    ```
    *Creates a `backup` directory and moves `example.txt` into it.*
   ![image](https://github.com/user-attachments/assets/b21f125a-31d4-4eb6-907f-cf5b54e8d0d1)


## Permissions

1. **Change the permissions of `example.txt` to read and write for the owner, and read-only for the group and others:**
    ```sh
    chmod 644 ~/linux_fundamentals/backup/example.txt
    ```
    *Sets the permissions of `example.txt` to read/write for the owner and read-only for others.*
   ![image](https://github.com/user-attachments/assets/125ff1c6-2918-4d06-8ab3-3dde7309ad0c)


2. **Verify the permission changes using `ls -l`:**
    ```sh
    ls -l ~/linux_fundamentals/backup/example.txt
    ```
    *Displays the permissions of `example.txt`.*
   ![image](https://github.com/user-attachments/assets/b3af3d5a-f210-4f09-9753-c826e3786038)
   

## File Modification

1. **Create a file named `example.txt` in  home directory:**
    ```sh
    touch ~/example.txt
    ```
    *Creates an empty file named `example.txt` in the home directory.*
   ![image](https://github.com/user-attachments/assets/4b4e2ebd-50b7-4186-98e5-944aad513d31)


2. **Change the owner of `example.txt` to a user named `student`:**
    ```sh
    sudo chown student ~/example.txt
    ```
    *Changes the ownership of `example.txt` to the user `student`.*
   ![image](https://github.com/user-attachments/assets/a37c03ea-10a3-41e3-acc0-327734a2c143)
   ![image](https://github.com/user-attachments/assets/20767a62-b7a1-4ccd-b955-d57dccf0ba1c)


3. **Change the group of `example.txt` to a group named `students`:**
    ```sh
    sudo chown :students ~/example.txt
    ```
    *Changes the group ownership of `example.txt` to the group `students`.*
   ![image](https://github.com/user-attachments/assets/843180e7-bd8c-4169-a48b-194e6135f24e)


4. **Verify the changes using `ls -l`:**
    ```sh
    ls -l ~/example.txt
    ```
    *Displays the updated owner and group information of `example.txt`.*
   ![image](https://github.com/user-attachments/assets/15d980ef-31e3-49d2-80f5-942b73f241db)


## Ownership

1. **Create a directory named `project` in  home directory:**
    ```sh
    mkdir ~/project
    ```
    *Creates a new directory named `project`.*
   ![image](https://github.com/user-attachments/assets/c24bc614-1206-4f4d-abb3-41b0fc76ddd5)


2. **Create a file named `report.txt` inside the `project` directory:**
    ```sh
    touch ~/project/report.txt
    ```
    *Creates an empty file named `report.txt` in the `project` directory.*
   ![image](https://github.com/user-attachments/assets/a0f5e4b2-ed97-4aac-84b9-4b1e4f12a703)


3. **Set the permissions of `report.txt` to read and write for the owner, and read-only for the group and others:**
    ```sh
    chmod 644 ~/project/report.txt
    ```
    *Sets the permissions of `report.txt`.*
   ![image](https://github.com/user-attachments/assets/a86c0470-fc5e-4c74-9752-9404701e0a1f)


4. **Set the permissions of the `project` directory to read, write, and execute for the owner, and read and execute for the group and others:**
    ```sh
    chmod 755 ~/project
    ```
    *Sets the permissions of the `project` directory.*
   ![image](https://github.com/user-attachments/assets/8f567803-aebb-4f2a-95b4-e2dcd7a12450)


5. **Verify the changes using `ls -l`:**
    ```sh
    ls -l ~/project/report.txt
    ls -ld ~/project
    ```
    *Displays the permissions of the `report.txt` file and the `project` directory.*
   ![image](https://github.com/user-attachments/assets/c37b2d74-8f60-4be9-badc-ae4406028650)
   ![image](https://github.com/user-attachments/assets/74a9cb6d-c9e5-45f5-b5a0-886b8391d175)


## User Add/Modify

1. **Create a new user named `developer`:**
    ```sh
    sudo useradd developer
    ```
    *Creates a new user named `developer`.*
   ![image](https://github.com/user-attachments/assets/312810cd-d000-4847-9437-56010048708e)


2. **Set the home directory of the user `developer` to `/home/developer_home`:**
    ```sh
    sudo usermod -d /home/developer_home developer
    ```
    *Changes the home directory of the user `developer`.*
   ![image](https://github.com/user-attachments/assets/bd23cd94-a561-4056-978d-c30e443113dc)
   ![image](https://github.com/user-attachments/assets/64e904de-aab5-4d76-a77e-8fcae23f2e98)
   

3. **Assign the shell `/bin/sh` to the user `developer`:**
    ```sh
    sudo usermod -s /bin/sh developer
    ```
    *Sets the login shell for `developer` to `/bin/sh`.*
   ![image](https://github.com/user-attachments/assets/6db7a08d-0028-4bd2-96ff-758e71dedfc6)


4. **Verify the new user's information:**
    ```sh
    getent passwd developer
    ```
    *Displays detailed information about the `developer` user.*
   ![image](https://github.com/user-attachments/assets/bdc2f892-3a92-4631-8a1c-373441986986)


5. **Change the username of the user `developer` to `devuser`:**
    ```sh
    sudo usermod -l devuser developer
    ```
    *Changes the username from `developer` to `devuser`.*
   ![image](https://github.com/user-attachments/assets/fb256bc9-e0e2-45da-8521-a6e725c7d9a9)


6. **Add `devuser` to a group named `devgroup`:**
    ```sh
    sudo groupadd devgroup
    sudo usermod -aG devgroup devuser
    ```
    *Creates a new group called `devgroup` and adds `devuser` to it.*
    ![image](https://github.com/user-attachments/assets/2fe34f54-abf2-4ecb-9498-6b950de5c2e4)


7. **Set the password of `devuser` to `devpass`:**
    ```sh
    sudo passwd devuser
    ```
    *Sets the password for `devuser`.*
    ![image](https://github.com/user-attachments/assets/d6822690-589e-4980-af96-774970d0e5e2)


8. **Verify the changes made to the user:**
    ```sh
    getent passwd devuser
    id devuser
    ```
    *Displays the information and group memberships of `devuser`.*
    ![image](https://github.com/user-attachments/assets/b1fb3453-9f81-42a6-94d2-d502e4f96754)


## Hard/Soft Link

1. **Create a file named `original.txt` in  home directory:**
    ```sh
    touch ~/original.txt
    ```
    *Creates an empty file named `original.txt`.*
   ![image](https://github.com/user-attachments/assets/2d7bb2ee-fdd9-4b66-bf70-7641e71ab5c3)


2. **Create a symbolic link named `softlink.txt` pointing to `original.txt`:**
    ```sh
    ln -s ~/original.txt ~/softlink.txt
    ```
    *Creates a symbolic link `softlink.txt` pointing to `original.txt`.*
   ![image](https://github.com/user-attachments/assets/b84c155d-eba8-4633-8b25-93c51fb7bf22)


3. **Verify the symbolic link:**
    ```sh
    ls -l ~/softlink.txt
    ```
    *Displays information about the symbolic link.*
   ![image](https://github.com/user-attachments/assets/1919e28f-983f-40e5-b44f-1259c921d97e)


4. **Delete the original file `original.txt` and check the status of the symbolic link:**
    ```sh
    rm ~/original.txt
    ls -l ~/softlink.txt
    ```
    *Deletes `original.txt` and checks the status of `softlink.txt`.*
   ![image](https://github.com/user-attachments/assets/02d6abee-5afa-48ac-be79-f9625640f916)


5. **Create a file named `datafile.txt` in  home directory:**
    ```sh
    touch ~/datafile.txt
    ```
    *Creates an empty file named `datafile.txt`.*
   ![image](https://github.com/user-attachments/assets/40327edb-0b38-4d00-9346-638a13024f5e)


6. **Create a hard link named `hardlink.txt` pointing to `datafile.txt`:**
    ```sh
    ln ~/datafile.txt ~/hardlink.txt
    ```
    *Creates a hard link `hardlink.txt` pointing to `datafile.txt`.*
    ![image](https://github.com/user-attachments/assets/2078909b-77ce-4526-9b5c-e0e7b6b6e5b2)


7. **Verify the hard link:**
    ```sh
    ls -l ~/datafile.txt ~/hardlink.txt
    ```
    *Displays information about both the original file and the hard link.*
    ![image](https://github.com/user-attachments/assets/a9de9197-fcbb-40b5-85c8-26efc4708431)


8. **Check the inode of both `datafile.txt` and `hardlink.txt`:**
    ```sh
    ls -i ~/datafile.txt ~/hardlink.txt
    ```
    *Displays the inode numbers for both files.*
    ![image](https://github.com/user-attachments/assets/ccc8e27a-532e-4471-82b4-c80d1ab60378)


9. **Delete the original file `datafile.txt` and observe the status of the hard link:**
    ```sh
    rm ~/datafile.txt
    ls -l ~/hardlink.txt
    ```
    *Deletes `datafile.txt` and checks the status of `hardlink.txt`.*
    ![image](https://github.com/user-attachments/assets/8bebb731-bcdf-4dbf-8a54-0aae9e67aaff)


10. **Find all `.txt` files in  home directory:**
    ```sh
    find ~ -name "*.txt"
    ```
    *Searches for all `.txt` files in  home directory.*
    ![image](https://github.com/user-attachments/assets/e93db0ad-955d-4932-88ad-c4c18ec2e094)


## Package Installation

1. **Update repo cache using `apt`/`apt-get`:**
    ```sh
    sudo apt update
    ```
    *Updates the package list.*
   ![image](https://github.com/user-attachments/assets/9c26b08d-465c-452f-abc7-b543ebb9f898)


2. **Install a package named `tree`:**
    ```sh
    sudo apt install tree
    ```
    *Installs the `tree` package.*
   ![image](https://github.com/user-attachments/assets/ebe4dadf-6e69-4bde-a0fc-0d9c98cd8c0d)


3. **Install gcloud CLI tool using apt:**
    ```sh
    sudo apt-get install apt-transport-https ca-certificates gnupg curl
    echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] http://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
    curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key --keyring /usr/share/keyrings/cloud.google.gpg add -
    sudo apt-get update && sudo apt-get install google-cloud-cli

    ![image](https://github.com/user-attachments/assets/f9daffb3-d166-4bf0-9da2-11f6ffe13c65)

