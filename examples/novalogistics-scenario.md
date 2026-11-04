# Input scenario – NovaLogistics B.V. (fictional)

NovaLogistics B.V. is a 120-employee freight forwarding SME based in Rotterdam. It runs its warehouse management system (WMS) on an on-premise Windows server, uses Microsoft 365 for email and files, and staff work remotely through a VPN. IT is partly outsourced to a small managed service provider (MSP) with permanent remote access.

Known issues from a short interview with the office manager:
- No MFA on the VPN; MFA only on some Microsoft 365 accounts.
- Backups are taken nightly to a NAS on the same network; restores have never been tested.
- IT admins share one domain administrator account.
- The WMS server runs an older Windows Server version and patching is done "when there is time".
- No security awareness training; supplier bank-detail changes are accepted by email.
- Laptops are not encrypted.
- The contract with the MSP contains no security clauses.
- The office depends on a single internet connection.
