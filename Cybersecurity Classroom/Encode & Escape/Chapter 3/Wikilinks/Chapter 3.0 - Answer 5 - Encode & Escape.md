
✅ **Correct Answer: B) Avoid using shell functions like `system()` and instead use safe, array-based APIs that pass the user input as a literal argument.**

💡 **Explanation:** Using **Safe APIs** is the mandatory defense against **[[Command Injection]]**. These APIs structurally prevent the user's input from being interpreted as a shell command sequence, neutralizing dangerous meta-characters like `;` and `|`.