
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>Amazon Data Protection Policy</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root { --fg:#111; --muted:#555; --bg:#fff; --card:#f7f7f9; }
    body { font: 16px/1.6 system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif; color:var(--fg); background:var(--bg); margin:0; padding:0; }
    .wrap { max-width: 860px; margin: 0 auto; padding: 24px; }
    h1, h2 { line-height:1.25; }
    h1 { margin-bottom: 8px; }
    .meta { color:var(--muted); margin-bottom: 24px; }
    nav { background:var(--card); padding:12px 16px; border-radius:12px; margin: 12px 0 24px; }
    nav a { margin-right: 12px; white-space:nowrap; }
    section { margin: 24px 0; }
    ul { margin: 8px 0 0 20px; }
    code { background:#f0f0f4; padding: 2px 6px; border-radius: 6px; }
  </style>
</head>
<body>
<div class="wrap">
  <h1>Amazon Data Protection Policy</h1>
  <div class="meta">Effective: September 18, 2025</div>

  <nav>
    <a href="#scope">Scope</a>
    <a href="#use">Use</a>
    <a href="#sharing">Sharing</a>
    <a href="#storage">Storage &amp; Retention</a>
    <a href="#security">Security</a>
    <a href="#logging">Logging &amp; Monitoring</a>
    <a href="#vuln">Vulnerability &amp; Change</a>
    <a href="#ir">Incident Response</a>
    <a href="#rights">Data Subject Rights</a>
    <a href="#subproc">Subprocessors</a>
    <a href="#intl">International Transfers</a>
    <a href="#changes">Changes</a>
  </nav>

  <section id="scope">
    <h2>1) Scope &amp; Roles</h2>
    <p>We handle Amazon Information obtained via SP-API to fulfill orders on behalf of the Amazon Seller. We act as a service provider/processor.</p>
  </section>

  <section id="use">
    <h2>2) Purpose Limitation (Use)</h2>
    <p>Amazon Information is used <strong>only</strong> to fulfill customer orders (create distributor POs, ship items, and post tracking). No marketing, unrelated analytics, profiling, or resale.</p>
  </section>

  <section id="sharing">
    <h2>3) Data Minimization &amp; Sharing</h2>
    <ul>
      <li>We process only what’s required to ship an order.</li>
      <li><strong>Third party:</strong> Essendant (drop-ship fulfillment) only.</li>
      <li><strong>Fields shared:</strong> recipient name, ship-to address, phone (if needed), and item/quantity for shipping.</li>
    </ul>
  </section>

  <section id="storage">
    <h2>4) Storage &amp; Retention</h2>
    <ul>
      <li>Shipping addresses are used in-memory to create the supplier order; <strong>not persisted</strong> to disk.</li>
      <li>Database stores operational data only (order ID/status/SKUs/timestamps).</li>
      <li>PII retained ≤ <strong>30 days</strong> after shipment/delivery, then deleted.</li>
      <li>Backups run daily, encrypted (AES-256), and exclude customer PII by design.</li>
    </ul>
  </section>

  <section id="security">
    <h2>5) Security Controls</h2>
    <ul>
      <li><strong>Encryption in Transit:</strong> All Amazon Information is transmitted using TLS 1.2 or higher.</li>
      <li><strong>Encryption at Rest:</strong> All disks are encrypted with AES-256 to protect stored data.</li>
      <li><strong>Access Control:</strong> Each administrator and service account uses a unique ID with least-privilege permissions, reviewed quarterly.</li>
      <li><strong>Password Policy:</strong> Passwords must be at least 12 characters long and contain uppercase, lowercase, numeric, and special characters; they expire every 90 days and cannot be reused from the previous five cycles.</li>
      <li><strong>Account Lockout:</strong> Accounts lock for 15 minutes after five failed login attempts.</li>
      <li><strong>Password Storage:</strong> Passwords are stored only as PBKDF2-HMAC-SHA256 hashes with unique salts; plaintext storage is prohibited.</li>
      <li><strong>Enforcement:</strong> Policies are enforced via PAM on Linux hosts and application-level validation for service accounts.</li>
      <li><strong>Authentication:</strong> Key-based SSH with passphrases is required; MFA is enabled wherever supported.</li>
      <li><strong>Network Security:</strong> Deny-by-default firewall, Fail2ban intrusion prevention, and no public database exposure.</li>
      <li><strong>Monitoring and Alerts:</strong> Continuous monitoring, automated alerts, and daily log reviews detect and respond to unauthorized activity.</li>
    </ul>
  </section>

  <section id="logging">
    <h2>6) Logging &amp; Monitoring</h2>
    <ul>
      <li>Logs are <strong>redacted</strong> (no PII/secrets); retained ≥ 90 days.</li>
      <li>Automated alerts for critical events; host intrusion/brute-force protection and daily reviews.</li>
    </ul>
  </section>

  <section id="vuln">
    <h2>7) Vulnerability &amp; Change Management</h2>
    <ul>
      <li><strong>Continuous Scanning:</strong> Dependency and package scans (e.g., <code>pip-audit</code>) run before each release; daily rootkit checks (e.g., <code>rkhunter</code>) verify host integrity.</li>
      <li><strong>Remediation Tracking:</strong> Vulnerabilities identified through scans or penetration tests are ticketed and tracked from discovery to closure.</li>
      <li><strong>Remediation Timelines:</strong> Critical – 7 days; High – 14 days; Medium – 30 days; Low – 90 days.</li>
      <li><strong>Verification:</strong> Each fix is verified by re-scan or code review before closure; unresolved critical items trigger automatic escalation to the administrator.</li>
      <li><strong>Testing &amp; Change Control:</strong> Changes are tested in staging, require documented approval, and include a rollback plan before production deployment.</li>
      <li><strong>Frequency:</strong> Vulnerability scans occur at least every 180 days; penetration testing is performed annually.</li>
    </ul>
  </section>

  <section id="ir">
    <h2>8) Incident Response</h2>
    <p>Detect → contain → eradicate → recover → post-mortem. We notify <code>security@amazon.com</code> of any confirmed incident involving Amazon Information within 24 hours and provide updates as required.</p>
  </section>

  <section id="rights">
    <h2>9) Data Subject Rights</h2>
    <p>We support applicable access/correction/deletion requests relayed by Amazon or the Seller.</p>
  </section>

  <section id="subproc">
    <h2>10) Subprocessors</h2>
    <p><strong>Essendant</strong> – fulfillment only, minimum necessary shipping fields, protections at least as strong as ours.</p>
  </section>

  <section id="intl">
    <h2>11) International Transfers</h2>
    <p>Where applicable, we apply appropriate safeguards consistent with law and Amazon policy.</p>
  </section>

  <section id="changes">
    <h2>12) Changes</h2>
    <p>We may update this Policy to reflect system or policy changes. The Effective date will be updated and material changes highlighted.</p>
    <p><strong>Contact:</strong> <a href="mailto:derrickdotson@protonmail.com">derrickdotson@protonmail.com</a></p>
  </section>
</div>
</body>
</html>
