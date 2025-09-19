
Amazon Data Protection Policy

Effective date: September 18, 2025

This Policy describes how our organization (“we,” “us”) handles Amazon Information obtained through the Selling Partner API (SP-API). It supplements our general Privacy & Data Handling Policy and is tailored to Amazon’s Acceptable Use Policy (AUP) and Data Protection Policy (DPP).

1) Scope & Roles

Scope: Amazon order and fulfillment data processed by our automation to fulfill orders placed by the Amazon Seller.

Role: We act as a service provider/processor to the Amazon Seller.

Amazon Information: Any data obtained via SP-API, including order identifiers, line items, and shipping PII strictly required for fulfillment.

2) Purpose Limitation (Use)

We use Amazon Information only to fulfill customer orders placed via Amazon (create purchase orders with our distributor, ship items, and post shipment/tracking). We do not use Amazon Information for marketing, analytics unrelated to fulfillment, profiling, or resale.

3) Data Minimization & Sharing

Minimum necessary: We process only what is required to ship an order.

Third parties: We share shipping details only with Essendant (our drop-ship fulfillment partner) for the sole purpose of fulfillment. No other third parties receive Amazon Information.

Fields shared with Essendant: Recipient name, ship-to address, phone (if required), and item/quantity data needed to ship.

4) Storage & Retention

PII persistence: We avoid storing shipping addresses at rest. Addresses are retrieved from Amazon, used in-memory to create the supplier order, then discarded.

Database contents: Operational records (order ID/status/SKUs/timestamps) only—no full shipping addresses.

Retention limits: Any Amazon PII present in temporary workflow artifacts is retained ≤ 30 days after shipment/delivery, then securely deleted. Operational, non-PII logs/metrics may be retained longer as permitted.

Backups: Daily, encrypted (AES-256). Backups exclude customer PII by design.

5) Security Controls

Encryption in transit: TLS 1.2+ for all external communications (Amazon, supplier).

Encryption at rest: Server disks and backups are stored on encrypted volumes (AES-256) with restricted access.

Access management: Unique user accounts (no shared logins), least-privilege permissions, and quarterly access reviews. Accounts are disabled within 24 hours of role change/departure.

Authentication: Key-based SSH with passphrases, strong passwords (≥12 chars; mixed case, digit, symbol) and MFA where supported.

Network protections: Host firewall (deny-by-default), Fail2ban to block abusive IPs, no public database exposure.

6) Logging & Monitoring

PII-safe logging: Application log filters automatically redact PII and secrets; logs contain operational events only.

Retention: Security/audit logs are retained ≥ 90 days for investigation and compliance.

Monitoring: Automated alerts for critical events; host-level intrusion and brute-force protection (UFW/Fail2ban). Routine review of logs and security reports.

7) Vulnerability & Change Management

Secure development: Dependency scanning (e.g., pip-audit) and security review before releases; failing checks block deployment.

Host integrity: Daily rootkit checks (e.g., rkhunter) and prompt OS/package patching.

Periodic testing: Vulnerability scans at least every 180 days and a penetration test annually (with tracked remediation SLAs: Critical 24–72h; High 7d; Medium 30d; Low 90d).

Change control: Staging/testing prior to production, approval required, and rollback plans documented.

8) Incident Response

Plan: Detect → contain → eradicate → recover → post-mortem, with evidence preservation and key rotation where needed.

Notification to Amazon: We will notify security@amazon.com
 of any confirmed Security Incident involving Amazon Information within 24 hours, and provide updates as required.

Customer/Seller notice: Where required by law or Amazon policy, affected parties will be informed.

9) Data Subject Rights

We support applicable data-subject requests (access, correction, deletion) received from Amazon or the Seller, consistent with contractual and legal requirements.

10) Subprocessors

Essendant – Order fulfillment (drop-ship). Receives only the minimum shipping fields necessary to deliver the order and is required to protect Amazon Information at least as strictly as we do.

11) International Transfers

If data is transferred across borders, we will use appropriate safeguards consistent with applicable laws and Amazon’s policies.

12) Changes to this Policy

We may update this Policy to reflect changes in our systems or in Amazon’s requirements. The “Effective date” will be updated, and material changes will be highlighted.

Contact: derrickdotson@protonmail.com
 
