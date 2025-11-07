### 🧠 **Definition and Risk 💥**

A **Buffer Overflow** (or Buffer Overrun) is a **[[Vulnerability]]** that occurs when a program attempts to write more data into a fixed-length memory buffer than it was allocated to hold.

- **Mechanism:** The excess data "overflows" the boundary of the buffer and overwrites adjacent memory locations.
    
- **Goal of Attacker:** The attacker typically overwrites adjacent memory that contains the program's return address, redirecting the execution flow to malicious code injected by the attacker.
    
- **Impact:** Leads to memory corruption, program crashes (**[[Denial of Service (DoS)]]**), and the most severe outcome, **Remote Code Execution (RCE)**.
    
- **Defense:** Using memory-safe languages, **Input Validation** to strictly enforce maximum string lengths, and compiler features like **stack canaries** to detect overwrites.