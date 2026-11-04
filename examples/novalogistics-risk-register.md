# Output – Risk register for NovaLogistics B.V.

> Generated with the `risk-register` skill from [the input scenario](novalogistics-scenario.md), then reviewed manually. Controls reference ISO/IEC 27001:2022 Annex A.

## Context
NovaLogistics B.V. is a 120-employee freight forwarder in Rotterdam whose operations depend on an on-premise WMS, Microsoft 365 and remote VPN access. Critical assets are the WMS and its shipment data, finance/payment processes, and the domain infrastructure that controls access to both.

## Risk table

| ID | Threat | Vulnerability | Asset | Likelihood | Impact | Level | Treatment | Proposed control |
|---|---|---|---|---|---|---|---|---|
| R1 | Ransomware | Backups on the same network, restores never tested | WMS server, file shares | 4 | 5 | **20** | Mitigate | Offline/immutable 3-2-1 backups with quarterly restore tests (A.8.13) |
| R2 | Credential theft (phishing, password spraying) | No MFA on VPN, partial MFA on M365 | Remote access, M365 | 4 | 4 | **16** | Mitigate | Enforce MFA on VPN and all M365 accounts (A.8.5) |
| R3 | Business email compromise / invoice fraud | No awareness training, bank-detail changes accepted by email | Finance & payments | 4 | 4 | **16** | Mitigate | Awareness training + call-back verification for bank-detail changes (A.6.3) |
| R4 | Misuse or compromise of admin credentials | Shared domain admin account, no accountability | Active Directory | 3 | 5 | **15** | Mitigate | Named admin accounts, least privilege, logging of privileged use (A.8.2) |
| R5 | Exploitation of known vulnerabilities | Outdated Windows Server, ad-hoc patching | WMS server | 3 | 4 | **12** | Mitigate | Patch management process with monthly cycle and upgrade plan (A.8.8) |
| R6 | Compromise via IT supplier | MSP has permanent remote access, no security clauses | Whole IT environment | 2 | 5 | **10** | Mitigate | Security requirements in the MSP contract, time-bound access (A.5.20) |
| R7 | Data breach from lost/stolen laptop (GDPR) | Unencrypted laptops | Customer & employee data | 3 | 3 | **9** | Mitigate | Full-disk encryption on all endpoints (A.8.1) |
| R8 | Internet outage | Single internet connection | Cloud services, remote access | 2 | 3 | **6** | Accept | Monitor; reassess if outages increase (A.8.14 as future option) |

## Top 3 priorities
1. **R1 – Ransomware:** set up an offline or immutable backup copy this month and run a full WMS restore test.
2. **R2 – Credential theft:** enable MFA on the VPN and all Microsoft 365 accounts, starting with admins and finance.
3. **R3 – Payment fraud:** introduce a mandatory phone call-back for any change of supplier bank details, plus a short phishing training.

## Assumptions
- Likelihood and impact are scored qualitatively from a short interview; no technical assessment was performed.
- NovaLogistics is assumed to have no cyber insurance; R1 could be partly transferred once controls are in place.
- NIS2 applicability (transport sector) was not assessed and should be checked.
