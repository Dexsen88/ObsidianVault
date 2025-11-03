### 🧠 **Definition and Purpose 🌐**

**Output Encoding** (or Contextual Output Escaping) is the process of converting input data into a safe, displayable format before it is rendered to the user's web browser.

- **Goal:** To prevent the browser from interpreting user-controlled data as executable code (like HTML or JavaScript) and instead force it to display the input as harmless text. This is the final, essential defense against **[[XSS]]** attacks.
    
- **Mechanism:** It transforms reserved characters (e.g., `<` becomes `&lt;`, `>` becomes `&gt;`) based on the specific context in which the data will be placed (e.g., HTML body, HTML attribute, or JavaScript string).
    
- **Timing:** Output Encoding is applied when data **leaves** the application (output) and is sent to the client, whereas **[[Input Validation]]** is applied when data **enters** the application (input). Both are required for **[[Defense in Depth]]**.