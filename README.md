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

---


# Managing Processes

---

### **1. `ps`**  
The `ps` command is used to display information about active processes running on the system. It provides a snapshot of the current processes.

#### **Common Options**:
- `ps`: Displays processes of the current shell session.
- `ps aux`: Shows all processes running on the system, along with detailed information.
  - `a`: Displays processes of all users.
  - `u`: Includes user and CPU/memory usage details.
  - `x`: Includes processes not attached to a terminal.

#### **Example**:
```bash
ps                          # Displays processes in the current session.
ps aux                      # Shows all active processes with details like PID, user, and resource usage.
ps -ef                      # Another common format for displaying process details.
```

---

### **2. `top`**  
The `top` command provides a real-time view of system resource usage, including CPU, memory, and process details. It is highly useful for monitoring system performance.

#### **Key Sections in `top` Output**:
- **Tasks**: Number of running, sleeping, or stopped processes.
- **CPU Usage**: Displays the percentage of CPU being utilized.
- **Memory Usage**: Displays physical and swap memory usage.
- **Processes**: Lists active processes sorted by CPU usage.

#### **Common Controls While Using `top`**:
- **q**: Quit `top`.
- **k**: Kill a process by entering its PID.
- **r**: Renice (change priority) of a process by entering its PID and new priority.
- **P**: Sort processes by CPU usage.
- **M**: Sort processes by memory usage.

#### **Example**:
```bash
top                         # Launches the `top` command to monitor resources in real-time.
top -d 5                    # Updates the display every 5 seconds instead of the default 3 seconds.
```

---

### **3. `kill`**  
The `kill` command is used to terminate a process by its Process ID (PID). It sends a signal to the process, instructing it to stop.

#### **Common Signals**:
- `SIGTERM` (15): Politely asks the process to terminate (default signal).
- `SIGKILL` (9): Forcibly kills the process if it doesn't respond to `SIGTERM`.
- `SIGHUP` (1): Restarts a process.

#### **Example**:
```bash
ps aux                      # Identify the PID of the process you want to terminate.
kill 1234                   # Sends SIGTERM to terminate the process with PID 1234.
kill -9 1234                # Sends SIGKILL to forcibly terminate the process.
kill -HUP 5678              # Restarts the process with PID 5678.
```

---

### **4. `htop`**  
The `htop` command is an interactive process viewer similar to `top`, but with a more user-friendly and visually appealing interface. It is not installed by default on many distributions but can be installed with package managers.

#### **Features of `htop`**:
- Color-coded display for CPU, memory, and swap usage.
- Allows scrolling through processes.
- Provides easy-to-use shortcuts for managing processes.

#### **Common Controls While Using `htop`**:
- **F2**: Open the setup menu to customize the display.
- **F3**: Search for a process.
- **F5**: Display tree view of processes.
- **F9**: Kill a process by selecting it.
- **F10**: Quit `htop`.

#### **Example**:
```bash
htop                        # Launches the `htop` interface.
sudo apt install htop       # Installs `htop` on Debian-based systems (if not installed).
```

---

### **Additional Notes**:
- **Viewing Processes**: Use `ps` for a snapshot and `top` or `htop` for real-time monitoring.
- **Killing Processes**: Be cautious while using `kill` to avoid terminating critical system processes.
- **Process Priority**: Use `nice` and `renice` to adjust process priorities instead of directly killing them when needed.
