Policies & Compliance
Amazon Data Protection Policy
Effective: September 18, 2025

1) Scope & Roles
We handle Amazon Information obtained via SP-API to fulfill orders on behalf of the Amazon Seller. We act as a service provider/processor.

2) Purpose Limitation (Use)
Amazon Information is used only to fulfill customer orders (create distributor POs, ship items, and post tracking). No marketing, unrelated analytics, profiling, or resale.

3) Data Minimization & Sharing
We process only what’s required to ship an order.
Third party: Essendant (drop-ship fulfillment) only.
Fields shared: recipient name, ship-to address, phone (if needed), and item/quantity for shipping.

4) Storage & Retention
Shipping addresses are used in-memory to create the supplier order; not persisted to disk.
Database stores operational data only (order ID, status, SKUs, timestamps).
PII is retained for no more than 30 days after shipment/delivery, then deleted.
Backups run daily, are encrypted (AES-256), and exclude customer PII by design.

5) Security Controls
Encryption in Transit: All Amazon Information is transmitted using TLS 1.2 or higher.
Encryption at Rest: All disks are encrypted with AES-256 to ensure confidentiality and integrity.
Access Control: Each administrator and service account uses a unique ID with least-privilege permissions, reviewed quarterly.
Password Policy: All passwords are at least 12 characters and include uppercase, lowercase, numbers, and special characters. Enforcement is handled through Linux PAM password policies with automatic expiration every 180 days. Key-based SSH with passphrases is required. Multi-factor authentication (MFA) is enforced for all human accounts. Accounts lock after multiple failed login attempts. All authentication events are logged and reviewed for anomalies.
Password Storage: All passwords are stored only as PBKDF2-HMAC-SHA256 hashes with unique salts; plaintext storage is prohibited.
Enforcement: Password and authentication policies are enforced through PAM on Linux hosts and application-level validation for service accounts.
Authentication: Key-based SSH with passphrases is required, and multi-factor authentication (MFA) is required for all human accounts with access to Amazon Information and enabled wherever supported.
Network Security: Firewall operates on a deny-by-default configuration with Fail2ban intrusion prevention and no public database exposure.
Monitoring & Alerts: Continuous monitoring, automated security alerts, and daily log reviews detect and respond to unauthorized or abnormal activity.

6) Logging & Monitoring
Logs are redacted (no PII or secrets) and retained for at least 90 days.
Automated alerts are generated for critical events; host intrusion, brute-force protection, and daily security reviews are performed.

7) Vulnerability & Change Management
Continuous Scanning: Dependency and package scans (e.g., pip-audit) are run before each release, and daily rootkit checks (e.g., khunter) verify host integrity.
Remediation Tracking: All findings are logged and tracked to closure in a central security log. Each issue is prioritized with strict timelines: Critical – 48 hours; High – 7 days; Medium – 30 days; Low – 90 days. The administrator verifies and documents each remediation. Vulnerability scans occur at least every 180 days or after major OS/software updates. Penetration testing is performed annually.
Testing & Change Control: All changes are tested in a staging environment before production deployment, require documented approval, and include a rollback plan.

8) Incident Response
Detect → contain → eradicate → recover → post-mortem. We notify security@amazon.com of any confirmed incident involving Amazon Information within 24 hours and provide updates as required.

9) Data Subject Rights
We support applicable access, correction, and deletion requests relayed by Amazon or the Seller.

10) Subprocessors
Essendant – fulfillment only; minimum necessary shipping fields; protections at least as strong as ours.

11) International Transfers
Where applicable, we apply appropriate safeguards consistent with law and Amazon policy.

12) Changes
We may update this Policy to reflect system or policy changes. The effective date will be updated and material changes highlighted.

Contact: derrickdotson@protonmail.com
Last updated: 2025-10-25 21:45 UTC
