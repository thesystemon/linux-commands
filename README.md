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


# **File Viewing and Editing**

---

### **1. `cat`**
The `cat` command displays the contents of a file. It can also concatenate multiple files and show them together.

#### **Common Options**:
- `cat file.txt`: Displays the contents of the file.
- `cat file1.txt file2.txt > merged.txt`: Combines file1 and file2 and saves the output to merged.txt.
- `cat -n file.txt`: Numbers each line in the output.

#### **Example**:
```bash
cat file.txt                  # Displays the entire content of file.txt.
cat file1.txt file2.txt       # Outputs the content of file1.txt followed by file2.txt.
cat -n file.txt               # Shows content with line numbers.
```

---

### **2. `less`**
The `less` command allows you to view file contents one page at a time. It's ideal for viewing large files.

#### **Common Controls While Using `less`**:
- **Space**: Scroll down one page.
- **b**: Scroll up one page.
- **q**: Quit `less`.

#### **Example**:
```bash
less file.txt                 # Opens file.txt for paginated viewing.
less /var/log/syslog          # Views large system log files one page at a time.
```

---

### **3. `nano`**
The `nano` command is a simple, user-friendly text editor for creating or modifying files.

#### **Common Controls in `nano`**:
- **Ctrl+O**: Save the file.
- **Ctrl+X**: Exit the editor.
- **Ctrl+K**: Cut a line.
- **Ctrl+U**: Paste a line.

#### **Example**:
```bash
nano file.txt                 # Opens file.txt for editing in the Nano text editor.
nano newfile.txt              # Creates and opens a new file named newfile.txt.
```

---

### **4. `vim`**
The `vim` command is a powerful and advanced text editor with extensive functionality.

#### **Basic Modes**:
- **Normal Mode**: Default mode for navigation and commands.
- **Insert Mode**: Enter text by pressing `i`.
- **Command Mode**: Save, quit, or execute commands by pressing `:`.

#### **Common Commands in `vim`**:
- `:w`: Save the file.
- `:q`: Quit vim.
- `:wq`: Save and quit.
- `:q!`: Quit without saving.

#### **Example**:
```bash
vim file.txt                 # Opens file.txt for editing in Vim.
vim newfile.txt              # Creates and opens a new file named newfile.txt in Vim.
```

---

### **5. `head`**
The `head` command shows the first few lines of a file. By default, it shows the first 10 lines.

#### **Common Options**:
- `head -n <number> file.txt`: Specify the number of lines to display.

#### **Example**:
```bash
head file.txt                # Displays the first 10 lines of file.txt.
head -n 5 file.txt           # Displays the first 5 lines of file.txt.
```

---

### **6. `tail`**
The `tail` command shows the last few lines of a file. By default, it displays the last 10 lines.

#### **Common Options**:
- `tail -n <number> file.txt`: Specify the number of lines to display.
- `tail -f file.txt`: Continuously display the last lines of a file, often used to monitor logs.

#### **Example**:
```bash
tail file.txt                # Displays the last 10 lines of file.txt.
tail -n 5 file.txt           # Displays the last 5 lines of file.txt.
tail -f /var/log/syslog      # Continuously monitors and displays new entries in the syslog file.
```

---

### **Additional Notes**:
- **Viewing Large Files**: Use `less` or `tail -f` for large files or logs to avoid cluttering the terminal.
- **Editing Tools**: While `nano` is beginner-friendly, `vim` offers advanced features for efficient editing.
- **Permissions**: Ensure you have the correct permissions to view or edit a file.


# **Managing Processes**

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
- 

# **System Information**


---

### **1. `uname`**  
The `uname` command displays system information, such as the kernel name, version, and operating system details.

#### **Common Options**:
- `uname`: Displays the kernel name (e.g., Linux).
- `uname -a`: Displays all available system information.
  - **Output Includes**:
    - Kernel name
    - Hostname
    - Kernel release and version
    - Machine hardware name
    - Operating system

#### **Example**:
```bash
uname                      # Displays the kernel name.
uname -a                   # Outputs detailed system information, such as:
                           # Linux hostname 5.15.0-73-generic #80-Ubuntu SMP Tue Apr 11 18:49:16 UTC 2023 x86_64 GNU/Linux
```

---

### **2. `df`**  
The `df` command shows information about disk space usage for file systems. This is helpful for monitoring disk usage and checking available space.

#### **Common Options**:
- `df`: Displays disk usage in blocks.
- `df -h`: Displays disk usage in a human-readable format (e.g., MB, GB).
- `df -T`: Shows the type of each file system.

#### **Example**:
```bash
df                        # Displays disk space usage in blocks.
df -h                     # Shows disk usage in human-readable units (e.g., 20G/100G).
df /home                  # Displays disk usage for the `/home` directory.
```

---

### **3. `du`**  
The `du` command estimates the disk space usage of files and directories.

#### **Common Options**:
- `du`: Displays disk usage for the current directory and its subdirectories.
- `du -h`: Shows sizes in human-readable units.
- `du -sh`: Summarizes total disk usage for a file or directory.
- `du -c`: Outputs a grand total of disk usage.

#### **Example**:
```bash
du folder                 # Displays disk usage for the `folder` directory.
du -sh folder             # Shows a human-readable summary of the `folder` size.
du -sh *                  # Summarizes sizes for all files and subdirectories in the current directory.
```

---

### **4. `free`**  
The `free` command displays information about memory usage, including total, used, and available memory.

#### **Common Options**:
- `free`: Displays memory usage in bytes.
- `free -m`: Displays memory usage in megabytes.
- `free -h`: Shows memory usage in a human-readable format.

#### **Output Fields**:
- **Total**: Total amount of memory.
- **Used**: Memory currently in use.
- **Free**: Unused memory.
- **Shared**: Memory shared between processes.
- **Buffers/Cache**: Memory used by buffers and cache.
- **Available**: Memory available for new applications.

#### **Example**:
```bash
free                      # Displays memory usage in bytes.
free -m                   # Shows memory usage in megabytes.
free -h                   # Outputs memory usage in a human-readable format.
```

---

### **5. `uptime`**  
The `uptime` command shows how long the system has been running, along with the current time, number of users, and load averages.

#### **Output Format**:
- **Current Time**: The current system time.
- **Up Time**: How long the system has been running.
- **Users**: Number of logged-in users.
- **Load Averages**: System load over the past 1, 5, and 15 minutes.

#### **Example**:
```bash
uptime                    # Example output:
                           # 14:32:18 up 2 days, 5:47, 3 users, load average: 0.23, 0.15, 0.10
```

---

### **Quick Summary of Use Cases**:
- **`uname`**: Check system kernel and OS information.
- **`df`**: Monitor file system and disk space usage.
- **`du`**: Analyze disk usage for files and directories.
- **`free`**: View memory usage and availability.
- **`uptime`**: Determine how long the system has been running.

