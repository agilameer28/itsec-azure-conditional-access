# Zero Trust Architecture: Entra ID Conditional Access Matrix

**Author:** Cloud IAM Architecture Team
**Objective:** Implement identity-based perimeter security using Microsoft Entra ID (formerly Azure AD) Conditional Access Policies (CAPs) to mitigate credential theft and unauthorized access.

## Conditional Access Policy Matrix

| Policy ID | Target Users | Target Cloud Apps | Conditions Evaluated | Access Controls Enforced |
| :--- | :--- | :--- | :--- | :--- |
| **CAP-01: Block Legacy Auth** | All Users | All Apps | Client App: Legacy Authentication clients (IMAP, POP3) | **Block Access** |
| **CAP-02: Enforce MFA Off-Network** | All Users | All Apps | Location: Any location *except* trusted Corporate IPs | **Grant Access:** Require Multi-Factor Authentication |
| **CAP-03: Admin Device Compliance** | Global Administrators | All Apps | Device State: Non-compliant or Unmanaged device | **Block Access** |
| **CAP-04: High Sign-in Risk Block** | All Users | All Apps | Sign-in Risk: High (e.g., Impossible Travel, Anonymous IP) | **Block Access** |

## Strategic Justification
By evaluating the **Risk**, **Location**, and **Device State** at every authentication attempt, this matrix ensures that compromised credentials alone are insufficient to breach the corporate environment, adhering strictly to Zero Trust principles.
