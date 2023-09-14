
## SHA-256
#### Digest text to hashed text
```js
const getHashCodeAsHexadecimal = async(text) => {
    if (!text) {
        return null;
    }
    try {
        const encoder = new TextEncoder();
        const buffer = encoder.encode(text);
        const raw = await crypto.subtle.digest("SHA-256", buffer);
        return Array.from(new Uint8Array(raw)).map(b => b.toString(16).padStart(2, "0")).join("");
    } catch (e) {}
    return null;
}
```
