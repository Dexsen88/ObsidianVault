
✅ **Correct Answer: B) Configuring NPM scopes (e.g., `@org`) in the `.npmrc` file to explicitly route private package requests to the trusted private registry.**

💡 **Explanation:** Scopes enforce a clear **Trust Boundary** by telling NPM exactly which registry to check first for internal packages, preventing the accidental download of a malicious public package with the same name.