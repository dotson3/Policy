# Privacy \& Data Handling Policy

# &nbsp;\*\*Effective Date:\*\* September 2025

# &nbsp;This Privacy \& Data Handling Policy describes how our organization ("we", "our", "us") manages

# &nbsp;Amazon Information when operating our order fulfillment automation with Essendant.

# &nbsp;Collection \& Use- Amazon Information is collected only through Amazon's Selling Partner API (SP-API).- Information is used strictly for order fulfillment purposes, including sending purchase orders to

# &nbsp;Essendant and shipping products to Amazon customers.- We do not use Amazon Information for analytics, marketing, or any unrelated processing.

# &nbsp;Sharing- Amazon Information is only shared with Essendant, our fulfillment partner, for the purpose of fulfilling

# &nbsp;orders.- The information shared includes order line items, shipping details, and purchase order numbers,

# &nbsp;transmitted securely via JSON/SFTP per Essendant specifications.- We do not share Amazon Information with any other third parties.

# &nbsp;Storage \& Retention- Amazon Information is stored temporarily in a local SQLite database on an encrypted server

# &nbsp;(AES-256/LUKS).- Logs and order data are automatically purged after \*\*31 days\*\*.- No data is stored offsite or in cloud services.

# &nbsp;Security- Data in transit is encrypted with TLS 1.2+.- Data at rest is encrypted with AES-256.- System access is restricted to a single administrator account protected with MFA and OS-level access

# &nbsp;controls.- Logs are redacted to remove PII and sensitive tokens before storage.

# &nbsp;Access Control- Only the system administrator has access to Amazon Information.- No shared accounts are used.- Access is role-based and granted strictly on a need-to-know basis.

# &nbsp;Backups- No persistent backups are retained beyond the 31-day window.- Any temporary backup files are encrypted with AES-256 and stored locally.

# &nbsp;Incident Response

# &nbsp;In the event of unauthorized access or breach:

# &nbsp;1. The affected system is isolated from the network.

# &nbsp;2. Credentials are rotated immediately.

# &nbsp;3. Logs are reviewed to identify scope.

# 4\. Stakeholders, including Amazon, are notified at \*\*security@amazon.com\*\* as required.

# &nbsp;5. The system is re-imaged and security controls are strengthened.

# &nbsp;Contact

# &nbsp;Questions regarding this policy can be directed to:

# &nbsp;\*\*Email:\*\* derrickdotson@protonmail.com

