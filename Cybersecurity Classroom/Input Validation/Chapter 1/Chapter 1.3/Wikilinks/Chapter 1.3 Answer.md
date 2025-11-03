✅ **Correct Answer: C) Canonicalization to decode the input to its simplest form.**

💡 **Explanation:** The input is currently double-encoded (`%25` is the URL encoding for `%`, which is then followed by `3C`). If the server doesn't fully decode the input via **Canonicalization** first, the whitelist rule will fail to match and block the character.