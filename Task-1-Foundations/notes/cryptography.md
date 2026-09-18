# Cryptography Fundamentals

> Fundamental cryptography concepts and practical encryption/decryption using OpenSSL.

---

## 🎯 Objective

Understand the basic concepts of cryptography, encryption, hashing, digital signatures, and secure communication.

---

## 1. What is Cryptography?

Cryptography is the practice of protecting information by transforming it into a form that unauthorized parties cannot easily understand.

It is commonly used to provide:

- Confidentiality
- Integrity
- Authentication
- Non-repudiation

---

## 2. CIA Triad and Cryptography

### Confidentiality

Ensures that information is accessible only to authorized users.

Encryption is commonly used to provide confidentiality.

### Integrity

Ensures that information has not been modified without authorization.

Cryptographic hashes can be used to verify integrity.

### Availability

Ensures that systems and information remain accessible when required.

Cryptography can support secure and reliable communication, but availability itself is not provided directly by encryption.

---

## 3. Encryption

Encryption converts readable plaintext into ciphertext using a cryptographic algorithm and key.

### Plaintext

The original readable information.

### Ciphertext

The encrypted form of the information.

### Decryption

The process of converting ciphertext back into plaintext.

---

## 4. Types of Encryption

### Symmetric Encryption

Symmetric encryption uses the same secret key for encryption and decryption.

Examples:

- AES
- ChaCha20

Advantages:

- Fast
- Suitable for encrypting large amounts of data

Challenge:

- The secret key must be securely shared between communicating parties.

### Asymmetric Encryption

Asymmetric encryption uses a key pair:

- Public key
- Private key

Examples:

- RSA
- ECC

The public key can be shared, while the private key must remain protected.

---

## 5. Hashing

A cryptographic hash function converts input data into a fixed-length digest.

Hashing is generally one-way and is not the same as encryption.

Common hashing algorithms include:

- SHA-256
- SHA-512

Example:

    echo -n "Hello World" | sha256sum

---

## 6. Digital Signatures

Digital signatures use asymmetric cryptography to provide:

- Authentication
- Integrity
- Non-repudiation

A private key is used to create a signature, and the corresponding public key can be used to verify it.

---

## 7. TLS

TLS (Transport Layer Security) is a cryptographic protocol used to secure network communication.

HTTPS uses TLS to protect web traffic.

TLS provides:

- Encryption
- Authentication
- Integrity

---

## 8. OpenSSL

OpenSSL is a widely used cryptographic toolkit that supports operations involving:

- Encryption and decryption
- Hashing
- Key generation
- Certificates
- Digital signatures
- TLS

Example:

    openssl version

---

## 9. Practical Cryptography

The practical cryptography exercise will use OpenSSL on the Kali Linux workstation.

The workflow will demonstrate:

1. Creating a plaintext file
2. Encrypting the file
3. Decrypting the ciphertext
4. Verifying the recovered plaintext

---

## 10. Practical Evidence

The following OpenSSL operations were performed on the Kali Linux workstation.

| Evidence | Practical Activity |
|---|---|
| `06-openssl-version.png` | OpenSSL version verification |
| `07-plaintext.png` | Plaintext file creation and verification |
| `08-encryption.png` | AES-256-CBC encryption using OpenSSL |
| `09-decryption.png` | AES-256-CBC decryption and plaintext recovery |
| `10-hash-verification.png` | SHA-256 hash comparison |

### Encryption

The plaintext file was encrypted using AES-256-CBC with salt and PBKDF2-based key derivation.

Command:

    openssl enc -aes-256-cbc -salt -pbkdf2 -in ~/crypto-test.txt -out ~/crypto-test.enc

### Decryption

The encrypted file was successfully decrypted using the same password.

Command:

    openssl enc -d -aes-256-cbc -pbkdf2 -in ~/crypto-test.enc -out ~/crypto-test-decrypted.txt

### Integrity Verification

SHA-256 hashes were calculated for both the original and decrypted files.

Command:

    sha256sum ~/crypto-test.txt
    sha256sum ~/crypto-test-decrypted.txt

The matching SHA-256 hashes verified that the decrypted file matched the original plaintext.

---

## 11. Verification Status

| Area | Status |
|---|---|
| Cryptography fundamentals | ✅ Documented |
| Symmetric encryption | ✅ Documented |
| Asymmetric encryption | ✅ Documented |
| Hashing | ✅ Documented |
| Digital signatures | ✅ Documented |
| TLS | ✅ Documented |
| OpenSSL version | ✅ Verified |
| AES-256-CBC encryption | ✅ Completed |
| AES-256-CBC decryption | ✅ Completed |
| SHA-256 integrity verification | ✅ Completed |
| Practical evidence | ✅ Captured |

---

## Conclusion

Cryptography provides mechanisms for protecting information through confidentiality, integrity, authentication, and non-repudiation. OpenSSL will be used to demonstrate practical encryption and decryption in the cybersecurity lab.
