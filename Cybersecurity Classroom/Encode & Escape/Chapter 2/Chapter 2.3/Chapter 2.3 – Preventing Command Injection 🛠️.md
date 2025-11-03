🌟 **Aisha’s Shell Shock** 
![[Aisha's Shell Shock.png]]
Aisha created an internal diagnostic tool that allowed system administrators to ping a network address by running the operating system command `ping <user_supplied_host>`. An attacker used the input `127.0.0.1; rm -rf /` and executed a malicious command on the server's operating system.

Elena: “This is **[[Command Injection]]**. The application failed to separate the _data_ (the IP address) from the _operating system command_. Just like **[[SQL Injection]]** breaks out of a database query and **[[XSS]]** breaks out of HTML, this attack breaks out of the shell command using a special character like a semicolon (`;`) or pipe (`|`).”

### 🧠 **Command Injection**

**[[Command Injection]]** (OS Command Injection) is an attack that allows an attacker to execute arbitrary commands on the host operating system where a vulnerable application is running.

- **Vulnerability:** Occurs when an application takes user input and passes it directly to an OS shell function (e.g., `system()`, `exec()`) without strict **[[Input Validation]]** or, more critically, without using a safe API.
    
- **Impact:** Extremely high severity, often leading to full system compromise, data theft, and violation of **[[Confidentiality]]** and **[[Integrity]]**.
    

### 💡 **The Mandatory Defense: Safe APIs**

Unlike **[[XSS]]** (which uses **[[Contextual Output Encoding]]**) or **[[SQL Injection]]** (which uses **[[Parameterization]]**), the primary defense against **[[Command Injection]]** is to avoid the execution environment entirely.

1. **Avoid Shell Execution:** The most secure practice is to avoid calling shell commands with user input if possible. Find the native API equivalent (e.g., using a built-in network library function for ping, instead of the external `ping` command).
    
2. **Use Safe APIs:** If you must call an external program, use the safe API provided by the language (e.g., `ProcessBuilder` in Java or the array-based execution methods in Python/PHP). These APIs treat every element of the command, including user input, as a literal string argument, preventing the OS shell from interpreting special characters like `;`, `&`, or `|` as command separators.
    

### 🎯 **Defense in Depth for Command Injection**
![[Defense in Depth for Command Injection.png]]

- **First Line:** Aggressive **[[Input Validation]]** using an **Allow-Listing** approach (e.g., only allow IP address format for a host input).
    
- **Second Line (Mandatory):** Use **Safe APIs** to execute commands, ensuring the user input is passed as a literal argument and not part of the executable command structure.
    
- **Last Resort Escaping:** If you absolutely cannot use a safe API (a rare and dangerous situation), you would have to manually **[[Escaping]]** or encoding shell meta-characters (like `&`, `|`, `;`, `\`, `$`) to neutralize their special meaning for the OS shell.
    

---

### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** What is the mandatory, structural defense against **[[Command Injection]]**, and why is it more effective than just manually escaping shell characters?

A) **[[Parameterization]]**; because it separates the command from the database.

B) **[[Contextual Output Encoding]]**; because it converts special characters to HTML entities.

C) Using Safe APIs (e.g., array-based execution); because the OS kernel treats the entire user input as a literal, unexecutable argument. 

D) **[[Data Minimization]]**; because it reduces the length of the command.

Click here to view the answer: [[Chapter 2.3 - Answer - Encode & Escape]]

---

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Define **[[Command Injection]]** and its severe impact.
    
- Explain the role of shell meta-characters (`;`, `|`, `&`) in the attack.
    
- Identify the mandatory defense: using **Safe APIs** instead of vulnerable shell functions.