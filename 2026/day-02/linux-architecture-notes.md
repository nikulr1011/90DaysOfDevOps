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

Processes
A process is a running program

A new process is created when a program starts another program

Each process has:

Its own memory
Its own Process ID (PID)
Example
ls
What happens:

The shell starts a new process for ls
The OS decides when it uses the CPU
ls finishes execution
Memory is freed
The shell keeps running
Process States
Running
Process is using the CPU or ready to use it
Sleeping
Process is waiting for something (input, disk, network)
This is normal behavior
Zombie
Process has finished execution
Parent process has not cleaned it up yet
ps aux | grep Z
Zombie processes do not use CPU or memory, but too many are harmful.

# 5 Commands used daily 
- ps or top : Provides process ID, memory usage, CPU time and command name which is crucial for monitoring system performance
              and troubleshooting.
- chmod : Changing permission of files.
- ssh : Provides secure shell connecting to remote server.
- systemctl : Managing system services (starting, stopping).
- df /du : df is used to monitor disk space usage and du is used to estimate size of a specific directory.
