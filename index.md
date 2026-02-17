# COBIT-Chain™ (Governance-First Assurance Framework)

**Author:** Taiwo Yusuf  
**Affiliation:** University of Wolverhampton (MBA)  
**Focus:** IT Governance • COBIT • Blockchain Governance • Clinical Trials • GxP Compliance • Digital Assurance

---

## Overview
COBIT-Chain™ is a governance-first assurance concept for regulated environments—designed to improve auditability, control evidence, and operational accountability across high-compliance processes (e.g., clinical trials and regulated IT operations). The framework emphasizes controls, traceability, and implementation blueprints rather than building a full platform.

---

## Micro-Governance Control Layer: Transitional Asset Custody Model (TACM)
This micro-governance control layer strengthens traceability and accountability during transitional “handoff” moments—when assets, devices, or service requests change custody before or during service execution. TACM establishes a lightweight chain-of-custody mechanism capturing custody transfers, timestamps, acknowledgments, condition attestation, and (where permitted) supporting evidence.

### Problem addressed
In regulated environments, compliance breakdowns frequently occur at handoff boundaries (pre-ticket, reassignment, shipping/returns, or loaner-to-replacement transitions). TACM reduces gaps such as unclear custody, missing evidence, and weak audit trails.

### Control outcomes
- Verifiable custody and accountability at each handoff point  
- Reduced loss, misrouting, and dispute risk  
- Improved audit readiness through structured evidence capture  
- Stronger alignment between operations and governance requirements  

### Implementation approach (prototype)
A lightweight prototype can be implemented using a simple workflow (e.g., Power Platform + SharePoint/Dataverse) with standardized fields, role-based confirmations, and optional evidence attachment using sanitized/approved artifacts.

*Note: This model is described generically as a regulated-pharma IT environment validation case; organizational identifiers are intentionally excluded.*

---

## COBIT 2019 Mapping (TACM)

### Primary processes
- **BAI09 – Manage Assets:** custody status, lifecycle transitions (loaner → replacement → return)  
- **BAI10 – Manage Configuration:** asset-user-ticket/CI relationship integrity  
- **DSS01 – Manage Operations:** standardized handoff execution and operational controls  
- **DSS02 – Manage Service Requests and Incidents:** traceability across ticket lifecycle  
- **DSS03 – Manage Problems:** trend exceptions and drive root-cause improvements  
- **MEA02 – Monitor, Evaluate and Assess the System of Internal Control:** evidence, exceptions, audit readiness reporting  

### Governance overlay (optional)
- **EDM03 – Ensure Risk Optimization:** reduces custody/compliance risk exposure  
- **APO12 – Manage Risk:** defines handoff risk scenarios and control responses  

---

## Architecture Diagram (TACM)
```mermaid
flowchart LR
  A[Custody Handoff Trigger<br/>Loaner, Replacement, Shipping, Reassignment] --> B[Create Handoff Record<br/>Asset ID, Request/Ticket Ref, Parties]
  B --> C[Sender Attestation<br/>Condition + Items Included]
  C --> D[Evidence Capture (Optional)<br/>Photo/Checklist/Notes]
  D --> E[Receiver Acknowledgment<br/>Timestamp + Acceptance]
  E --> F[Governance Controls Applied<br/>Policy, Retention, Audit Trail]
  F --> G[Operational Execution<br/>Repair/Replace/Ship/Return]
  G --> H[Closure + Final Custody State<br/>Return label, delivery confirmation]
  H --> I[Reporting & Assurance<br/>Metrics, Exceptions, Audit Evidence]
