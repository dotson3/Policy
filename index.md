
**Effective Date:** September 2025

This Privacy & Data Handling Policy describes how our organization (“we”, “our”, “us”) manages **Amazon Information** when operating our order fulfillment automation with Essendant.

## Collection & Use
- Amazon Information is collected only through Amazon’s Selling Partner API (SP-API).
- Information is used strictly for order fulfillment (sending purchase orders to Essendant and shipping products to Amazon customers).
- We do **not** use Amazon Information for analytics, marketing, or any unrelated processing.

## Sharing
- Amazon Information is shared only with **Essendant** for the purpose of fulfilling orders.
- Shared data includes order line items, shipping details, and purchase order numbers, transmitted securely via JSON/SFTP per Essendant specifications.
- We do **not** share Amazon Information with any other third parties.

## Storage & Retention
- Amazon Information is stored temporarily in a local SQLite database on an **encrypted Linux server** (AES-256/LUKS).
- Logs are retained for **at least 90 days** for security and audit purposes.
- Customer PII is retained **no longer than 30 days after order delivery** and is automatically purged by a daily job.
- No data is stored offsite or in cloud services.

## Security
- Data in transit is encrypted with **TLS 1.2+**.
- Data at rest is encrypted with **AES-256**.
- System access is restricted to a single administrator account protected with **SSH keys and MFA/OTP**.
- Logs are sanitized to remove PII and sensitive tokens before storage.

## Access Control
- Only the system administrator has access to Amazon Information.
- No shared accounts are used.
- Access is granted strictly on a need-to-know basis and **reviewed monthly**.

## Backups
- No persistent backups are retained beyond retention windows.
- Any temporary backup files are encrypted with AES-256 and stored locally, then deleted by policy.

## Incident Response
In the event of unauthorized access or breach:
1. The affected system is isolated from the network.
2. Credentials and keys (SP-API, SFTP, env secrets) are rotated immediately.
3. Logs are collected for forensics to determine scope.
4. Amazon is notified at **security@amazon.com** within **24 hours** if Amazon Information may be impacted.
5. The system is re-imaged from a clean baseline, patches applied, automation restored, and controls strengthened.

## Contact
Questions regarding this policy can be directed to:  
**Email:** derrickdotson@protonmail.com
