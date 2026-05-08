# Outershield SME SOC Framework

**Developed by Outershield Security LLC | Albuquerque, New Mexico**

A lightweight, open-source Security Operations Center (SOC) 
automation framework specifically architected for small and 
medium-sized enterprises (SMEs) and resource-constrained 
critical infrastructure operators.

---

## The Problem

Small and medium-sized enterprises represent the majority of 
U.S. critical infrastructure operators — rural hospitals, 
municipal utilities, regional financial institutions, and 
small manufacturers. These organizations face the same 
adversaries as Fortune 500 companies but operate without 
dedicated security teams, enterprise budgets, or threat 
intelligence capabilities.

Current SOC automation solutions assume:
- A dedicated security operations team
- Enterprise-grade hardware and cloud budgets
- Specialized security engineering expertise

**None of these assumptions hold for SMEs.**

The result is a structural security gap that nation-state 
actors, ransomware groups, and opportunistic threat actors 
actively exploit. Congressional testimony before the House 
Subcommittee on Cybersecurity and Infrastructure Protection 
(March 2023) identified this gap as one of the most 
consequential vulnerabilities facing American critical 
infrastructure.

---

## The Solution

The Outershield SME SOC Framework adapts proven enterprise 
SOC automation architecture into a deployment model 
optimized for organizations with:

- Limited or no dedicated security staff
- Constrained IT budgets
- No existing SIEM or EDR infrastructure
- Minimal security engineering expertise

This framework enables a single IT generalist to operate 
security monitoring and incident response capabilities that 
would otherwise require a full SOC team.

---

## Architecture
┌─────────────────────────────────────────────────────┐
│                   Detection Layer                    │
│                  Wazuh (Open Source)                 │
│         Log aggregation · Alert generation           │
│              Endpoint + network telemetry            │
└─────────────────────┬───────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────┐
│                Orchestration Layer                   │
│                 n8n (Self-hosted)                    │
│        Workflow automation · API integrations        │
│           Alert enrichment · Routing logic           │
└─────────────────────┬───────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────┐
│              Case Management Layer                   │
│             TheHive (Open Source)                    │
│      Incident tracking · CIRCIA-ready documentation │
│         Response playbooks · Audit trail             │
└─────────────────────────────────────────────────────┘

**Core Stack:**
- **Wazuh** — open-source SIEM and XDR for detection
- **n8n** — self-hosted workflow orchestration
- **TheHive** — open-source incident case management
- **Claude API (Anthropic)** — AI-powered alert 
  summarization and triage assistance

**Design Principles:**
- Zero licensing cost for core components
- Deployable on a single low-cost virtual machine
- No cloud dependency (fully on-premises capable)
- Pre-configured for SME threat profiles

---

## Modules

### 🔴 Module 1 — CVE Intelligence Notifications
*Status: Active Development*

Automated vulnerability notification system that pulls 
daily from the CISA Known Exploited Vulnerabilities (KEV) 
catalog and NIST NVD API, filters by the organization's 
specific tech stack, and delivers LLM-summarized 
professional security advisories directly to the SME 
owner's inbox.

Each notification includes:
- Plain-English vulnerability summary (Claude API)
- Business impact assessment
- Prioritized remediation guidance
- Severity classification (Critical / Medium / Low)

### 🟡 Module 2 — Automated SOC Event-to-Case Pipeline
*Status: Planned — Q3 2026*

Wazuh-to-TheHive automated pipeline that moves security 
detections from alert generation through enrichment to 
case creation without manual intervention. Includes 
pre-built playbooks for:
- Phishing triage
- Ransomware detection and containment
- Credential abuse response
- Unauthorized access alerting

### 🟢 Module 3 — SME Threat Intelligence Feed
*Status: Planned — Q4 2026*

Curated threat intelligence integration connecting SME 
environments to CISA advisories, FBI threat alerts, and 
sector-specific ISAC feeds relevant to the organization's 
industry vertical.

---

## Research Foundation

This framework is the practical implementation arm of 
ongoing cybersecurity research conducted through 
Outershield Security LLC, building on:

**Published Research:**
- *CLOSO Framework: AI-Human Collaborative Security 
  Operations Center Workflows* — IRE Journals, 
  December 2024. Co-authored by Chinemelum Nmesoma 
  Umealajekwu et al. Establishes the theoretical and 
  operational foundations for AI-augmented SOC automation 
  architectures implemented in this framework.

**Related Projects:**
- [SOC Automation Lab 2.0](https://github.com/chineme-code/soc-automation-lab-2.0) 
  — predecessor enterprise-grade SOC automation pipeline 
  (Splunk · Sysmon · n8n · GPT-4o · AbuseIPDB · Slack)

**Ongoing Research:**
- XAI-powered intrusion detection using XGBoost and SHAP 
  interpretability analysis on the CICIDS 2017 dataset, 
  targeting peer-reviewed publication in IEEE Access or 
  Journal of Information Security and Applications 
  (Elsevier)

---

## Target Deployment Environments

- Rural and community hospitals
- Municipal water and utility systems
- Small regional financial institutions
- Local government and municipal networks
- Small manufacturers in critical supply chains
- Nonprofit organizations handling sensitive data

---

## Current Status

| Module | Status | Target |
|--------|--------|--------|
| CVE Intelligence Notifications | 🔄 Active Development | Q2 2026 |
| SOC Event-to-Case Pipeline | 📋 Architecture Design | Q3 2026 |
| SME Threat Intelligence Feed | 📋 Planned | Q4 2026 |
| Deployment Documentation | 📋 In Progress | Q3 2026 |

---

## About Outershield Security LLC

Outershield Security LLC is an independent cybersecurity 
research and consulting entity registered in New Mexico, 
focused exclusively on developing accessible, 
cost-effective security frameworks for SMEs and 
resource-constrained critical infrastructure operators.

**Research Lead:** Chinemelum Nmesoma Umealajekwu, M.S.  
CompTIA Security+ | CompTIA CySA+  
M.S. Cybersecurity and Business Analytics, University of 
New Mexico (GPA: 4.0)

---

## Contributing

This is an open-source research project. Contributions, 
issue reports, and deployment feedback from SME 
environments are welcome. See CONTRIBUTING.md for 
guidelines.

---

## License

MIT License — free for use, modification, and deployment 
by any organization.

---

*This project is conducted in the national interest of 
strengthening U.S. critical infrastructure cybersecurity 
through accessible, scalable security automation for 
under-resourced operators.*
