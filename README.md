### **Basic Linux Commands: File and Directory Management**
---

### **1. `ls`**
The `ls` command lists the files and directories in the current directory or the specified directory.

#### **Common Options**:
- `ls`: Basic listing.
- `ls -l`: Long format listing (shows permissions, owner, group, size, and modification time).
- `ls -a`: Show all files, including hidden ones (files starting with `.`).
- `ls -lh`: Long format with human-readable sizes.

#### **Example**:
```bash
ls                # Lists files and directories in the current directory.
ls -l             # Lists with detailed information.
ls -a             # Lists hidden files (e.g., .bashrc).
ls -lh            # Displays sizes in KB, MB, GB, etc.
```

---

### **2. `cd`**
The `cd` command is used to navigate between directories.

#### **Common Options**:
- `cd`: Takes you to your home directory.
- `cd /path/to/directory`: Navigates to the specified directory.
- `cd ..`: Moves up one directory level (parent directory).
- `cd -`: Switches to the previous directory.

#### **Example**:
```bash
cd /var/log         # Navigate to the /var/log directory.
cd ..               # Go to the parent directory.
cd ~/Documents      # Navigate to the Documents directory in the home folder.
cd -                # Switch to the previous directory.
```

---

### **3. `pwd`**
The `pwd` command prints the current working directory.

#### **Example**:
```bash
pwd                # Outputs the current directory path, e.g., /home/user.
```

---

### **4. `mkdir`**
The `mkdir` command creates new directories.

#### **Common Options**:
- `mkdir directory_name`: Creates a directory.
- `mkdir -p /path/to/directory`: Creates parent directories if they don't exist.

#### **Example**:
```bash
mkdir mydir         # Creates a directory named "mydir" in the current location.
mkdir -p /tmp/test  # Creates the /tmp/test directory, including parent directories if missing.
```

---

### **5. `rm`**
The `rm` command removes files or directories.

#### **Common Options**:
- `rm file_name`: Deletes a file.
- `rm -r directory_name`: Recursively deletes a directory and its contents.
- `rm -f`: Force deletion without prompting.

#### **Example**:
```bash
rm myfile.txt       # Deletes a file named "myfile.txt".
rm -r mydir         # Deletes the "mydir" directory and its contents.
rm -rf mydir        # Deletes without confirmation, even if protected.
```

**⚠️ Warning**: Be cautious with `rm -rf` as it deletes everything without confirmation.

---

### **6. `cp`**
The `cp` command copies files or directories.

#### **Common Options**:
- `cp source_file destination_file`: Copies a file.
- `cp -r source_directory destination_directory`: Recursively copies a directory.
- `cp -i`: Prompts before overwriting.

#### **Example**:
```bash
cp file1 file2      # Copies file1 to file2.
cp -r dir1 dir2     # Copies all files and subdirectories from dir1 to dir2.
cp -i file1 file2   # Prompts before overwriting file2 with file1.
```

---

### **7. `mv`**
The `mv` command moves or renames files and directories.

#### **Common Options**:
- `mv source destination`: Moves or renames.
- `mv -i`: Prompts before overwriting.

#### **Example**:
```bash
mv oldname newname  # Renames "oldname" to "newname".
mv file1 /tmp       # Moves "file1" to the /tmp directory.
mv -i file1 file2   # Prompts before overwriting file2 with file1.
```

---

### **Additional Notes**:
- **File and Directory Permissions**: Ensure you have the necessary permissions when working with files or directories.
- **Use with `sudo`**: For operations in system directories or files, you might need `sudo`.
