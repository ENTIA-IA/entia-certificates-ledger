# ENTIA Certificates Ledger

Public, immutable record of all digital certificates issued by ENTIA Notaría Digital.

Each certificate file contains:
- **cert_id**: Unique certificate identifier
- **file_hash_sha256**: SHA-256 hash of the certified document
- **timestamp_utc**: RFC 3161 timestamp
- **tsa_provider**: Timestamp Authority
- **aware_seal**: HMAC-SHA256 integrity seal
- **entity_id**: Certified entity identifier

## Verification

Verify any certificate at: https://entia.systems/api/notaria/verify/{cert_id}

## Standard

RFC 3161 · eIDAS · SHA-256 · Aware Seal

---
PrecisionAI Marketing OÜ · EE102780516 · Tallinn, Estonia