

> [!Info] Overview
> 🔐 **Cryptographic Failures** (formerly known as **Sensitive Data Exposure** in OWASP Top 10) occur when **data is not properly encrypted** or is stored/transmitted in an insecure manner.
> 
> ### **Why is it Dangerous?**
> - Attackers can **steal personal or financial data**.
> - Weak encryption can be **easily cracked** using brute force.
> - Leads to **data breaches, identity theft, and financial loss**.

---
## **Description**

Cryptographic failures happen when an application:

- **Stores sensitive data in plaintext** (without encryption).
- Uses **weak or outdated encryption algorithms** (e.g., MD5, SHA-1).
- Exposes **encryption keys in public repositories**.
- Uses **insecure transmission methods** (e.g., HTTP instead of HTTPS).
- **Fails to properly encrypt session tokens**, allowing attackers to hijack user sessions.

### **Common Causes of Cryptographic Failures**

❌ **Storing passwords in plaintext** instead of hashing them.  
❌ **Using weak encryption** (e.g., DES, RC4).  
❌ **Hardcoding encryption keys in code** (making them easy to extract).  
❌ **Not using HTTPS** (allowing attackers to intercept sensitive data).  
❌ **Using the same key for all encryption operations**, making it easy to decrypt.

---

## **How to Prevent Cryptographic Failures?**

### Use Strong Hashing for Passwords 🔐

- Store passwords using **bcrypt, Argon2, or PBKDF2** (avoid MD5 and SHA-1).

## Use Secure Encryption Algorithms 🔗

- Use **AES-256** for encrypting sensitive data.

### Always Use HTTPS 🌐

- Never send sensitive data over **HTTP** or unsecured email.

### Protect Encryption Keys

- Store keys in **secure vaults** (e.g., AWS Secrets Manager, HashiCorp Vault).
- Never **hardcode keys in your code** or commit them to GitHub.

### Use Secure Storage for Data

- Encrypt databases with **Transparent Data Encryption (TDE)**.
- Avoid **storing sensitive data unless absolutely necessary**.