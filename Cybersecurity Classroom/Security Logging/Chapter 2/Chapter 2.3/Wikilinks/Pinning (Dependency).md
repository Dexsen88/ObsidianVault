### 🧠 **Definition and Mechanism 📍**

**Pinning** is the security practice of explicitly defining dependencies in the project manifest (`package.json`) using **exact version numbers** (e.g., `1.2.3`) without using fuzzy semantic versioning operators (`^` or `~`).

- **Goal:** To prevent unexpected updates (even patch or minor versions) from being automatically installed, thus mitigating the risk of introducing a new, unaudited **[[Vulnerability]]** or **[[Malware]]** through an automatic update.
    
- **Mechanism:** When combined with a lock file, **Pinning** ensures that any attempt to update a package requires a manual, deliberate change to the `package.json` file and a corresponding **[[Software Composition Analysis (SCA)]]** audit.
    
- **Mandate:** Production code should always use pinned versions to maximize control over the **[[Supply Chain Attack]]** surface and ensure **[[Determinism (Dependency)]]**.