# Cryptography – Digital Chain of Custody

## Project Overview

This project demonstrates a secure digital evidence chain-of-custody workflow using:

- SHA-256 hashing
- RSA 2048-bit key pairs
- Digital signatures
- Multi-party verification

The goal is to preserve integrity, authentication, non-repudiation, and traceability across multiple custodians.

All operations were performed locally in Kali Linux using OpenSSL.

---

## Security Objectives Demonstrated

### 1. Integrity
Evidence integrity is preserved using SHA-256 hashing. Any modification to the file produces a different hash value.

### 2. Authentication
Each custodian has a unique RSA key pair. Digital signatures confirm the identity of the signer.

### 3. Non-Repudiation
Because only the private key holder can generate a valid signature, custodians cannot deny participation.

### 4. Chain Traceability
Each transfer between custodians is documented and cryptographically signed.

---

## Workflow Summary

1. Evidence file created
2. SHA-256 hash generated
3. Custodian A signs evidence hash
4. A → B transfer documented and signed
5. B verifies integrity
6. B → C transfer documented and signed
7. Signatures verified successfully

---

## Project Structure

- `evidence/` – Original evidence file
- `outputs/` – Hashes, signatures, and transfer records
- `keys/` – Public keys only (private keys removed for security)
- `screenshots/` – Verification proof

---

## Signature Verification Example

Example verification command:

```
openssl dgst -sha256 -verify custodianB_public.pem -signature handoff_B_to_C.sig handoff_B_to_C.txt
```

Output:
```
Verified OK
```

---

## Ethical & Security Note

Private keys were generated locally and intentionally excluded from this repository.

This project is for educational and defensive cybersecurity demonstration purposes only.