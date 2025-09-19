
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
    <a href="#storage">Storage & Retention</a>
    <a href="#security">Security</a>
    <a href="#logging">Logging & Monitoring</a>
    <a href="#vuln">Vulnerability & Change</a>
    <a href="#ir">Incident Response</a>
    <a href="#rights">Data Subject Rights</a>
    <a href="#subproc">Subprocessors</a>
    <a href="#intl">International Transfers</a>
    <a href="#changes">Changes</a>
  </nav>

  <section id="scope">
    <h2>1) Scope & Roles</h2>
    <p>We handle Amazon Information obtained via SP-API to fulfill orders on behalf of the Amazon Seller. We act as a service provider/processor.</p>
  </section>

  <section id="use">
    <h2>2) Purpose Limitation (Use)</h2>
    <p>Amazon Information is used <strong>only</strong> to fulfill customer orders (create distributor POs, ship items, and post tracking). No marketing, unrelated analytics, profiling, or resale.</p>
  </section>

  <section id="sharing">
    <h2>3) Data Minimization & Sharing</h2>
    <ul>
      <li>We process only what’s required to ship an order.</li>
      <li><strong>Third party:</strong> Essendant (drop-ship fulfillment) only.</li>
      <li><strong>Fields shared:</strong> recipient name, ship-to address, phone (if needed), and item/quantity for shipping.</li>
    </ul>
  </section>

  <section id="storage">
    <h2>4) Storage & Retention</h2>
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
      <li>In transit: TLS 1.2+; At rest: encrypted disks (AES-256).</li>
      <li>Access: unique accounts, least-privilege, quarterly reviews; key-based SSH with passphrases; MFA where supported.</li>
      <li>Network: firewall (deny-by-default), Fail2ban, no public DB exposure.</li>
    </ul>
  </section>

  <section id="logging">
    <h2>6) Logging & Monitoring</h2>
    <ul>
      <li>Logs are <strong>redacted</strong> (no PII/secrets); retained ≥ 90 days.</li>
      <li>Automated alerts for critical events; host intrusion/brute-force protection and daily reviews.</li>
    </ul>
  </section>

  <section id="vuln">
    <h2>7) Vulnerability & Change Management</h2>
    <ul>
      <li>Dependency scans (e.g., pip-audit) and security review before release; blocking policy for critical/high issues.</li>
      <li>Daily rootkit checks (e.g., rkhunter); prompt OS/package patching.</li>
      <li>Vulnerability scans ≥ every 180 days; penetration test annually; tracked SLAs: Critical 24–72h, High 7d, Medium 30d, Low 90d.</li>
      <li>Changes tested in staging; approval + rollback plan required.</li>
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
    <p>We may update this Policy to reflect system or policy changes. Effective date will be updated and material changes highlighted.</p>
    <p><strong>Contact:</strong> derrickdotson@protonmail.com • 

