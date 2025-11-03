### 🧠 **Definition and Mechanism 📂**

**Path Traversal** (or Directory Traversal) is a vulnerability that allows an attacker to read arbitrary files on a server by exploiting application code that incorrectly handles file or directory paths provided by the user.

- **Mechanism:** An attacker inputs special characters like `../` (dot-dot-slash) to navigate outside of the application's root directory and access sensitive files, such as `/etc/passwd` or application configuration files.
    
- **Input Validation Defense:** The strongest defense is **Whitelisting** the input to allow only specific, safe characters (letters, numbers, hyphens) and **disallowing** any file path separators (`/` or `\`) or the `.` and `..` sequences.
    
- **Impact:** A successful attack violates **[[Confidentiality]]** by accessing sensitive configuration or system files.