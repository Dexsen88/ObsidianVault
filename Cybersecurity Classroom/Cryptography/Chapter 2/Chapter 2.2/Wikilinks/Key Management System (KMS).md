### 🧠 **Definition and Role 📦**

A **Key Management System (KMS)** is a software service or application dedicated to the lifecycle management of cryptographic keys. It acts as a highly secured, central authority for keys.

- **Goal:** To centralize key operations and reduce the risk of individual applications exposing keys. It ensures keys are dispensed only to authenticated and authorized processes, enforcing the **[[Principle of Least Privilege]]**.
    
- **Functions:** Generating strong keys, rotating keys on a schedule, securely storing them, and providing auditing logs for all key access requests.
    
- **Architecture:** In cloud environments, the KMS often manages keys that are ultimately protected by **[[Hardware Security Module (HSM)]]** devices.