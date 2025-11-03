### 🧠 **The Fundamental Security Model 🛡️**

The **CIA Triad** (Confidentiality, Integrity, and Availability) is the most foundational model for developing and evaluating security policies and practices in any information system.
![[CIA.png]]
- **Interdependence:** All three pillars must be protected. Compromising one pillar often weakens the security of the others (e.g., losing **[[Integrity]]** can lead to granting unauthorized **[[Confidentiality]]** access).
    
- **Role in Validation:** **Input Validation** is a key control because it directly defends all three: preventing data modification (Integrity), stopping data theft (**[[Confidentiality]]**), and avoiding application crashes (**Availability**).