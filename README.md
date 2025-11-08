# 🔍 threat-hunting

Proactive threat hunting lab built on top of my SOC environment  
(Wazuh SIEM, Suricata IDS, Proxmox lab-core-network, soc-alert-automation).

This repo focuses on **hypothesis-driven hunts**, repeatable methodology, and turning good hunts into **detections and runbooks**.

---

## 🎯 Goals

- Practice **structured threat hunting** across:
  - Network (Suricata)
  - Endpoint / logs (Wazuh)
  - Cloud / IAM (AWS/Azure lab)
- Document hunts as **stories**: hypothesis → data → findings → action.
- Convert successful hunts into:
  - Detection rules (Sigma / Wazuh / Suricata)
  - Playbooks / runbooks
  - Training material for future SOC roles.

---

## 📂 Repository Structure

```text
threat-hunting/
├── README.md
├── docs/
│   ├── methodology.md          # overall hunting process + checklist
│   ├── hunting-playbook.md     # step-by-step guide for running a hunt
│   └── references.md           # links/notes (ATT&CK, Sigma, etc.)
├── hunts/
│   ├── dns-tunneling.md        # full story: hypothesis → evidence → conclusion
│   ├── ssh-bruteforce.md
│   ├── web-shell-detections.md
│   └── cloud-console-anomalies.md
├── detections/
│   ├── sigma/
│   │   └── win_susp_powershell.yml
│   ├── wazuh-rules/
│   │   └── wazuh_dns_tunnel_rule.xml
│   └── suricata-rules/
│       └── suricata_dns_anomaly.rules
├── notebooks/
│   ├── wazuh-dns-tunnel-hunt.ipynb
│   ├── suricata-ssh-bruteforce-hunt.ipynb
│   └── cloud-api-anomaly-hunt.ipynb
└── exports/
    ├── sample-logs/
    │   ├── wazuh-dns-alerts.json
    │   └── suricata-ssh-alerts.json
    └── dashboards/
        └── wazuh-threat-hunting-dashboard.json
