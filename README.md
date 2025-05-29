# Security-Project_Secure-Password-Manager

## 🔐 Notable Contributions

- [password_manager](https://github.com/jannepetter/password_manager)  
  Contributed to feature development, bug fixes, or improvements in this secure password management application built with Python and cryptographic libraries.
## 🖥️ User Interface

The application features a clean and responsive GUI built with **Tkinter** and **ttkbootstrap**. This setup provides a modern look while maintaining the simplicity and cross-platform compatibility of native Python UI libraries.

---

## 🗃️ Database & Encryption

This password manager uses **SQLite** for local data storage and implements **AES-256 encryption** to ensure strong data security.

- All user data is **stored in encrypted form**.
- During read operations, the data is **decrypted at runtime** using a key derived from the user's **password and username**.
- If the user forgets their **username or password**, the encryption key cannot be recreated, and **data recovery becomes impossible**.
- **All fields are encrypted** in the database except the **entry ID**.
- The database supports **only a single user** for enhanced control and simplicity.

---

## 🔐 Key Derivation & Brute-Force Protection

- The encryption key is generated using **5000000 iterations** of a key derivation function, making it **computationally expensive** to brute force.
- On an average machine, generating a single key takes approximately **2.5 seconds**, significantly slowing down any brute-force attempts.
- Users are encouraged to choose **strong passwords** to maximize security.

---

## 🛡️ Enhanced Security Measures

To further harden the system against attacks:

- A **random initialization vector (IV)** is used for each encryption, ensuring that the **same plaintext always results in different ciphertext**.
- **Padding** is applied to mask the true length of the data, preventing adversaries from inferring information based on ciphertext size.

These measures together make the stored data **resistant to analysis**, even if an attacker gains direct access to the database file.

---

## ✅ Running Unit Tests

For usage examples and validation tests, see the `/tests` directory.

Run all unit tests with:

```bash
python3 -m unittest discover -s tests

