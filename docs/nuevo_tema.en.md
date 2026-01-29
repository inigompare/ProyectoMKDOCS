# UNIX: Process and Task Control / Personal Task

**Author:** Iñigo Durán Sanz

This guide explores process management in UNIX/Linux systems, covering from background execution to priority management and signals.

---

## Practical Exercises

### 1. The `yes` command

The `yes` command sends an infinite output of "yes" to the terminal.

- **Observation**: When executed, it saturates the terminal and "dirties" the screen with continuous text.

### 2. Interruption with CTRL+C

We can stop the "aggressive" execution of the previous command using the interrupt key combination.

![Image 2](img/imagen_2.png)

### 3. Redirection to `/dev/null`

We run `yes > /dev/null`.

- **Result**: The screen no longer fills with text (output is discarded), but the terminal remains busy and we don't get the _prompt_ back.

### 4. Interruption again

We cancel the previous process with `CTRL+C` to regain control.

![Image 4](img/imagen_4.png)

### 5. Background Execution (`&`)

We run `yes > /dev/null &`.

- **Result**: The system returns the _prompt_ immediately.
- **Data**: We get the **Job Number** and the **PID** (Process ID).

![Image 5](img/imagen_5.png)

### 6. Job Status

We use the `jobs` command to verify that the process is still running in the background.

![Image 6](img/imagen_6.png)

### 7. Normal Termination (`kill`)

We terminate the process using the `kill %1` command (or the corresponding job number) and verify with `jobs`.

![Image 7](img/imagen_7.png)

### 8. Termination by PID

We launch the process again and this time we "kill" it using its specific **PID**: `kill <PID>`.

![Image 8](img/imagen_8.png)

### 9. Suspend Processes (`CTRL+Z`)

We launch the process in the foreground and pause/suspend it with `CTRL+Z`.

![Image 9](img/imagen_9.png)

### 10. Verify Suspension

We check with `jobs` that the status is "Stopped".

![Image 10](img/imagen_10.png)

### 11. Resume in Foreground (`fg`)

We bring the suspended task to the front with the `fg` command.

![Image 11](img/imagen_11.png)

### 12. Process Priority (`nice`/`renice`)

To run a process with lower priority (higher nice value, e.g. 10), we use `nice`. To change it during execution, `renice`.

- _Note: `-10` usually requires root privileges to increase priority._

![Image 12](img/imagen_12.png)

### 13. Suspend again

We temporarily stop the execution with `CTRL+Z`.

![Image 13](img/imagen_13.png)

### 14. Resume in Background (`bg`)

We reactivate the process but keep it in the background with `bg`.

![Image 14](img/imagen_14.png)

### 15. Multiple Process Management

We repeat the management (suspend, `bg`, `fg`) using commands like `sleep 1000` to have several simple processes.

![Image 15](img/imagen_15.png)

### 16. Complex Demonstration

Scenario with at least 5 simultaneous processes: suspending, resuming and sending signals to several of them.

![Image 16](img/imagen_16.png)

### 17. Interactive Visualization (`top` / `htop`)

Use of interactive tools to view resource consumption in real time.

![Image 17](img/imagen_17.png)

### 18. The `ps` command and its variants

Use of the `ps` command with various different combinations to filter and format the output:

??? "ps commands"

    **Examples:**

    1.  `ps`
    2.  `ps aux`
    3.  `ps -ef`
    4.  `ps -ejH`
    5.  `ps -t`
    6.  `ps -ax --forest`
    7.  `ps -e -o`
    8.  `ps -eo`

![Image 18](img/imagen_18.png)

### 19. The `pstree` command

Process tree visualization to understand the parent-child hierarchy.

![Image 19](img/imagen_19.png)
![Image 19](img/imagen_19_1.png)
![Image 19](img/imagen_19_2.png)

### 20. Child Processes and Terminal (`gnome-calculator`)

When launching `gnome-calculator` from the terminal and closing the latter, the calculator closes.

- **Reason**: The calculator is a child process of the shell; when the parent dies, the children die (SIGHUP).

![Image 20](img/imagen_20.png)

### 21. Using `nohup`

Run `nohup gnome-calculator`. When closing the terminal, the calculator **remains open**.

- **Reason**: `nohup` ignores the hangup signal (HUP).

![Image 21](img/imagen_21.png)

### 22. Total Independence

With `nohup`, closing the application (calculator) does not affect the terminal, and closing the terminal does not affect the application. They are independent.

### 23. `nohup` Output Redirection

To avoid the default `nohup.out` file and discard the output:
`nohup gnome-calculator > /dev/null 2>&1 &`
This redirects both standard output and error to "nothing".

![Image 23](img/imagen_23.png)
