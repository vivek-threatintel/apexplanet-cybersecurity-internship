# OpenSSL Encryption and Decryption

> Practical demonstration of symmetric encryption and decryption using OpenSSL on Kali Linux.

---

## Objective

Demonstrate file encryption and decryption using OpenSSL and AES-256-CBC.

The practical exercise verifies that plaintext can be encrypted into ciphertext and recovered using the correct password.

---

## 1. OpenSSL Version

The installed OpenSSL version was verified using:

    openssl version

Output:

    OpenSSL 3.6.3 9 Jun 2026

---

## 2. Create Plaintext File

A plaintext test file was created:

    echo "Cybersecurity fundamentals test." > ~/crypto-test.txt

The contents were verified using:

    cat ~/crypto-test.txt

Output:

    Cybersecurity fundamentals test.

---

## 3. Encrypt the File

AES-256-CBC encryption was performed using OpenSSL:

    openssl enc -aes-256-cbc -salt -pbkdf2 -in ~/crypto-test.txt -out ~/crypto-test.enc

A password was supplied when prompted.

The encrypted file was then verified:

    ls -lh ~/crypto-test.enc

The resulting file was stored as:

    ~/crypto-test.enc

---

## 4. Decrypt the File

The encrypted file was decrypted using:

    openssl enc -aes-256-cbc -salt -pbkdf2 -in ~/crypto-test.enc -out ~/crypto-test-decrypted.txt

The same encryption password was supplied when prompted.

The resulting decrypted file was:

    ~/crypto-test-decrypted.txt

---

## 5. Verify Decrypted Content

The decrypted file was inspected using:

    cat ~/crypto-test-decrypted.txt

The expected plaintext is:

    Cybersecurity fundamentals test.

This confirms that the encrypted file can be recovered when the correct password is provided.

---

## 6. Hash Verification

SHA-256 hashing was also demonstrated using:

    echo -n "Cybersecurity fundamentals test." | sha256sum

A cryptographic hash provides a fixed-length digest that can be used to verify data integrity.

Hashing is different from encryption because a cryptographic hash is designed to be one-way.

---

## 7. Practical Evidence

The following screenshots document the OpenSSL practical exercise:

- `screenshots/06-openssl-version.png`
- `screenshots/07-plaintext.png`
- `screenshots/08-encryption.png`
- `screenshots/09-decryption.png`
- `screenshots/10-hash-verification.png`

---

## Security Relevance

OpenSSL is commonly used for:

- Symmetric encryption
- Decryption
- Hashing
- Key generation
- Certificate operations
- Digital signatures
- TLS-related operations

AES-256-CBC provides confidentiality when used correctly with a strong password and appropriate key derivation.

The `-salt` option adds a random salt to the encrypted output, while `-pbkdf2` uses PBKDF2 for password-based key derivation.

---

## Verification Status

| Area | Status |
|---|---|
| OpenSSL installation | Completed |
| Plaintext creation | Completed |
| AES-256-CBC encryption | Completed |
| File decryption | Completed |
| Plaintext recovery | Completed |
| SHA-256 hashing | Completed |
| Practical screenshots | Completed |

---

## Conclusion

The OpenSSL practical demonstrated AES-256-CBC encryption and decryption of a plaintext file on Kali Linux. The recovered plaintext was verified after decryption, and SHA-256 hashing was also demonstrated for integrity verification.
