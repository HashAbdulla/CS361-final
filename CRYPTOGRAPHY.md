
---

## 🔐 Core Cryptographic Concepts

### 🔑 Definitions

* **Cryptology** = Cryptography (creating secure messages) + Cryptanalysis (breaking them)
* **Encryption** = Converting plaintext into ciphertext
* **Decryption** = Converting ciphertext back to plaintext
* **Key / Cryptovariable** = Secret used in encryption/decryption
* **Work Factor** = Effort (time/resources) required to break a cipher

---

## 📊 Cipher Types & Methods

### ✨ Substitution Ciphers

* Replace one value with another.
* **Monoalphabetic** = One substitution set
* **Polyalphabetic** = Multiple substitution sets
* **Vigenère Cipher** = Uses 26 different cipher alphabets

### 🔄 Transposition Cipher

* Rearranges plaintext based on a fixed pattern.
* Can operate at bit or byte level.

### 🔁 XOR Function

* Compares bits:

  * Same = 0
  * Different = 1
* Simple but weak; do not use alone for sensitive data

### 🧪 Vernam Cipher (One-Time Pad)

* Uses random key used once per message
* Unbreakable if implemented correctly

### 📚 Book-Based Ciphers

* Use books to generate or share encryption keys

  * *Book Cipher*, *Running Key Cipher*, *Template Cipher*

---

## 🔐 Hashing Functions

| Feature          | Description                                     |
| ---------------- | ----------------------------------------------- |
| Purpose          | Message integrity, identity confirmation        |
| Output           | Fixed-length message digest                     |
| No Key Required? | ✅ Yes                                           |
| Use Case         | Passwords, integrity checks, digital signatures |

* Example: **Message Authentication Code (MAC)**

📝 **MCQ Tip**: Hash functions **do not require keys**

---

## 🔁 Symmetric vs Asymmetric Encryption

| Feature  | Symmetric (Private Key) | Asymmetric (Public Key)           |
| -------- | ----------------------- | --------------------------------- |
| Key Type | One shared key          | Public & private key pair         |
| Speed    | Fast                    | Slower                            |
| Examples | DES, 3DES, AES          | RSA                               |
| Use Case | Bulk encryption         | Secure key exchange, digital sig. |

### 🔒 Symmetric Encryption

* **DES**: 56-bit key, outdated
* **3DES**: Stronger, slower
* **AES**: Current standard (NIST); fast, secure

### 🔓 Asymmetric Encryption

* **RSA**: First public-key algorithm; still widely used

📝 Scenario Tip: For **secure remote access**, use hybrid approach—**asymmetric for key exchange**, **symmetric for data encryption**

---

## 🔀 Hybrid Cryptography

* Combine symmetric + asymmetric encryption
* Most common: **Diffie-Hellman Key Exchange** (secure shared key negotiation)

---

## 🧾 Digital Signatures & Certificates

### 🖋 Digital Signature

* Confirms sender identity
* Uses **asymmetric encryption**
* Ensures **nonrepudiation** (can’t deny sending)

📝 **MCQ Tip**: Nonrepudiation = can’t deny sending the message

### 🧾 Digital Certificate

* Contains key + identifying info
* Verified by Certificate Authority (CA)
* Uses **X.509 v3 standard** structure

### 🔐 Public Key Infrastructure (PKI)

* Framework to manage keys, certificates, authorities
* Components:

  * **CA** – Certifies identities
  * **RA** – Handles registration
  * **Certificate directories**
  * **Management protocols**

---

## 🕵️‍♂️ Steganography

* Hides data in other media (e.g., images, audio)
* Not true encryption but adds confidentiality
* Commonly used in **.bmp, .mp3, .wav**, etc.

---

## 🔗 Secure Protocols

### 🔐 Secure Web Communications

| Protocol    | Function                                 |
| ----------- | ---------------------------------------- |
| **SSL/TLS** | Secure channel via public-key encryption |
| **HTTPS**   | HTTP + SSL                               |
| **S-HTTP**  | Encrypts individual HTTP messages        |

### 📧 Secure Email

| Protocol   | Details                                              |
| ---------- | ---------------------------------------------------- |
| **S/MIME** | Public-key + MIME                                    |
| **PEM**    | Uses 3DES + RSA                                      |
| **PGP**    | Hybrid; open-source; uses IDEA cipher for encryption |

### 💳 Secure Transactions

| Protocol | Details                                |
| -------- | -------------------------------------- |
| **SET**  | Developed by Visa/MasterCard, uses DES |

### 📡 Wireless Security

| Protocol      | Notes                                             |
| ------------- | ------------------------------------------------- |
| **WEP**       | Weak; 40-bit static keys                          |
| **WPA/WPA2**  | Dynamic session keys, 128-bit encryption          |
| **Bluetooth** | Short-range; needs controls to avoid exploitation |

📝 **Scenario Tip**: For “ShopSmart Solutions” setting up **secure e-commerce**, use:

* **HTTPS/SSL**
* **PKI and digital certificates**
* **AES for encryption**
* **WPA2 for wireless**

---

## 🔁 IPSec & PGP

### 🔒 IPSec (for TCP/IP Security)

* Open protocol for secure IP traffic
* Uses:

  * **Diffie-Hellman** (key exchange)
  * **Digital Certificates** (identity)
  * **Symmetric encryption** (data encryption)

### 📧 Pretty Good Privacy (PGP)

* Hybrid cryptosystem for **email and file encryption**
* Offers:

  * Authentication
  * Encryption
  * Compression
  * Segmentation
  * Key management

---

## 💼 As the CISO for ShopSmart Solutions (Scenario-Ready Guidance)

### 🧠 Common Scenarios You May Face:

**Q: How should I secure customer transactions on ShopSmart’s website?**

* Use **HTTPS with SSL**
* Implement **PKI and digital certificates**
* Encrypt sensitive fields (credit card info) using **AES**
* Validate integrity via **digital signatures**

**Q: What if ShopSmart’s email communication is being intercepted?**

* Enforce use of **PGP or S/MIME**
* Ensure all sensitive email is **digitally signed and encrypted**

**Q: What encryption should we use for internal file storage?**

* Use **AES** for speed and security
* For integrity, store **hash digests (SHA-256)** of each file

**Q: How do I ensure nonrepudiation in legal communications?**

* Use **digital signatures**
* Store **digital certificates** from a trusted CA

**Q: How should remote workers connect securely to our systems?**

* Require **VPN (with IPSec)**
* Use **multi-factor authentication**
* Exchange session keys using **Diffie-Hellman**

---

## 🧠 Fast Facts for MCQs & Definitions

* 🔁 **Symmetric = One key**, **Asymmetric = Key pair**
* 🔒 **AES = Modern symmetric encryption standard**
* 📜 **Digital Certificate = Identifies owner + public key**
* ❌ **Hashing ≠ Encryption**; hashing is one-way
* 🔐 **Nonrepudiation = Can’t deny having sent a message**
* 🔍 **Steganography = Hiding info, not encrypting**

---
