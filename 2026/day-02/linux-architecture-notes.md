# Day 02 – Linux Architecture, Processes, and systemd

## Task
Today’s goal is to **understand how Linux works under the hood**.

# Core components of Linux :
- Hardware :
The physical component where OS is installed.
- Kernel :
The heart of Linux. The central core that directly controls hardware, processes, memory. Interface between hardware and software. Machine understands kernel language.
- Shell :
Interactive way to talk to kernel using commands.
- GUI :
Graphical user interface for visual interaction.
- System Libraries : 
Collections of pre-written functions that applications use to request services from the kernel.
- System Utilities : 
Programs and tools (like ls, cp, grep) that perform specific tasks, managing files, users, and system operations.

# Processes in Linux

Processes are instances of running programs. For ex. if you do pin ww.google.com then ping process is created.
You can list processes using ps(ps ax, ps ef) or top commands. 
## Process states
- running : Active process.
- sleeping : Idle process.
- Stopped : Process suspended by signal SIGSTOP (Ctrl+Z, Ctrl+C). It can be resumed by a SIGCONT signal.
- Zombie : The process has terminated, but its entry in the process table still exists because its parent process has not 
           yet read its exit status.



## Process & Process Manegement 
- Everything in linux is processes ,even a cmd executed by user is process .
    - `a cmd enter by user on shell`
    - `shell  calls forks() & created a child process`
    - `child process calls exec()`
    - `kernel schedule it for execution`
- Some of process states as follow 
    - `Running : process is running on cpu`
    - `Sleeping : waiting for i/o`
    - `Zombie : process is finished but not cleaned`
- Some of important commands for process manegement are as follow 
    - `top: its shows all process used to monitor & troubleshoot`
    - `htop: you can horizontally & vertically scroll all process`
    - `ps -a : is used to display all process ` 
    - `kill -9 PID: forcefully terminate a process`

---

## Systemd/init Process

- It is a first process lanuched by kernal ,its pid is always 1 
- It is responsible for starting system service 
- Some of the imp commands of systemd as follow 
    - `systemctl status ssh: it will show ssh service status `
    - `systemctl start ssh: it will start ssh service`
    - `systemctl stop ssh: it will stop ssh service`
    - `systemctl enable ssh: it will start ssh service automatically after server boot`
    - `systemctl restart ssh : it will restart ssh service`
    - `systemctl list-units : it will show all active units loaded in systemd`
    - `journalctl -u ssh : it will used to see a logs of systemd processes`




--- 



# 5 Commands used daily 
- ps or top : Provides process ID, memory usage, CPU time and command name which is crucial for monitoring system performance
              and troubleshooting.
- chmod : Changing permission of files.
- ssh : Provides secure shell connecting to remote server.
- systemctl : Managing system services (starting, stopping).
- df /du : df is used to monitor disk space usage and du is used to estimate size of a specific directory.
