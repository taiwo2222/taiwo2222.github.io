# COBIT-Chain™

**Governance-first operational control model for regulated IT environments**

**Author:** Taiwo Yusuf  
**Academic affiliation:** University of Wolverhampton (MBA)  
**Framework foundation:** COBIT 2019  
**Focus:** IT Governance - Asset lifecycle control - Digital assurance - GxP-aligned operations

---

## What this is

COBIT-Chain™ is a COBIT-aligned governance model that turns everyday IT operations into measurable, time-bound controls.  
The goal is not to build another platform. The goal is to design lightweight control layers that strengthen accountability, traceability, and audit readiness in regulated environments.

This model was validated through an applied prototype in a regulated pharmaceutical IT setting. Organizational identifiers are intentionally excluded.

---

## Why it was needed

In high-compliance environments, risk often shows up in small handoff gaps:

- Devices aging in stock until policy flags them
- Shipping carts relying on informal ownership
- Asset handoffs without timestamp evidence
- SLA expectations without consistent enforcement

COBIT defines governance expectations. The applied control layer makes them practical in daily operations.

---

## Applied operational governance modules

### 1) Transitional asset custody control
A structured handoff record whenever custody changes, capturing:
- sender and receiver accountability
- timestamped confirmation
- status progression
- traceable linkage to operational work

**Outcome**
- stronger chain-of-custody evidence
- fewer disputes and “who had it last” gaps
- improved audit traceability

**COBIT alignment**
- BAI09 - Manage Assets  
- DSS01 - Manage Operations  
- DSS02 - Manage Service Requests and Incidents  
- MEA02 - Monitor, Evaluate and Assess Internal Control  

---

### 2) FedEx cart governance control
This module turns shipping dispatch into a controlled, time-bound process.

**How it works**
- weekly rotation assigns a clear owner
- device staged triggers status = Pending FedEx Dispatch
- SLA deadline is set automatically to 4:45 PM
- 4:40 PM reminder if anything is still pending
- 4:45 PM confirmation logs timestamp and closes the loop
- 4:46 PM missed SLA triggers automatic escalation and exception logging

**Outcome**
- clear ownership and cutoff time
- reminders before breach, escalation only when needed
- timestamps as basic evidence trail

**COBIT alignment**
- DSS01 - Manage Operations  
- APO12 - Manage Risk  
- MEA02 - Monitor, Evaluate and Assess Internal Control  

---

### 3) TechBar device aging and FIFO control
Intune flags idle devices at day 60. This module adds early governance enforcement.

**How it works**
- reminders start 10 days before the 60-day threshold
- reminders continue until devices are remediated and records updated
- remediation path: reimage or replace with already-imaged units
- FIFO logic prioritizes older stock first

**Outcome**
- fewer devices drifting into non-compliant state
- improved inventory rotation and throughput
- stronger alignment between endpoint policy and operations

**COBIT alignment**
- BAI09 - Manage Assets  
- DSS01 - Manage Operations  
- DSS03 - Manage Problems  
- MEA02 - Monitor, Evaluate and Assess Internal Control  

---

## Governance analytics layer (Power BI)

Power BI was used as the assurance and visibility layer to monitor:
- SLA compliance rates (shipping and dispatch)
- aging buckets (0-30, 30-60, 60+)
- approaching-threshold inventory
- turnaround time from reminder to remediation
- exception frequency trends over time

This turns operational activity into measurable control performance.

**COBIT alignment**
- MEA02 - Monitor, Evaluate and Assess Internal Control  
- EDM03 - Ensure Risk Optimization (governance oversight of risk exposure)  

---

## Implementation approach

Prototype implementation leveraged:
- Microsoft Power Platform (workflow and control screens)
- SharePoint lists (structured control records)
- Intune (endpoint state flags)
- Power BI (governance analytics)
- ServiceNow alignment (operational workflow reference)

The emphasis was governance enforcement and evidence capture, not system complexity.

---

## Architecture diagram

```mermaid
flowchart TB
  A[COBIT 2019 Governance Framework<br/>EDM - APO - BAI - DSS - MEA]
  B[Operational Control Modules]
  C1[Asset Custody Control]
  C2[FedEx Cart SLA Control]
  C3[Device Aging and FIFO Control]
  D[Application Layer<br/>Power Platform - SharePoint - Intune]
  E[Assurance Layer<br/>Power BI Monitoring and Reporting]
  A --> B
  B --> C1
  B --> C2
  B --> C3
  C1 --> D
  C2 --> D
  C3 --> D
  D --> E
  E --> A

