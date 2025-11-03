### 🧠 **Definition and Vulnerability 🛠️**

**Command Injection** (or OS Command Injection) is a vulnerability that allows an attacker to execute arbitrary operating system commands on the server hosting the application. This attack is often executed by leveraging application functions that pass unsanitized user input to a system shell command.

- **Root Cause:** Failure to strictly separate the data from the command when invoking external programs using functions like `system()`, `exec()`, or backticks.
    
- **Impact:** High-severity, typically leading to full server compromise, data exposure, and loss of control over the application environment.
    
- **Mandatory Defense:** Use **Safe APIs** (array-based execution) that pass user input as a literal argument to the program, thereby bypassing the OS shell interpreter.