# 📂 Surebet Calculator

This repository serves as a reference document for the business logic and validated test scenarios of the **Sports Arbitrage (Surebet) Calculator**, ensuring the transparency and reliability of the tool delivered to the client.

The objective is to demonstrate that the application correctly handles all requirements, from identifying profit to validating negative scenarios.

---

## 🎯 Application Goal

The Surebet Calculator translates the complex arbitrage concept into an operational tool. It must:
1.  **Validate** if the combination of Odds (2, 3, or 4) results in a guaranteed profit ($\text{Sum of Reciprocals} < 1$).
2.  **Calculate** the profit percentage ($\text{ROI}$).
3.  **Distribute** the total stake value of $\text{R}\$ 100.00$ proportionally across each Odd, ensuring the net return.

---

## ✅ Critical Test Cases (Proof of Concept)

The scenarios below are the functional proof of the system's robustness.

### Scenario 1: High Opportunity Success (2 Odds)

| Attribute | Details |
| :--- | :--- |
| **Description** | The system finds and calculates a high-profit scenario and distributes the stake correctly. |
| **Input Odds** | **1.89** and **2.48** |
| **Logic Validation** | $\frac{1}{1.89} + \frac{1}{2.48} = 0.932$ ($\text{Result} < 1$). |
| **UI Result** | **Surebet Found!** ($\text{7.26\%}$ Profit) |
| **Stake Distribution (R$ 100.00)**| R$56.75 and R$43.25 |
---

### Scenario 2: Multiple Outcome Complexity (3 Odds)

| Attribute | Details |
| :--- | :--- |
| **Description** | The system correctly handles increased complexity and distributes the stake among 3 outcomes. |
| **Input Odds** | **2.6**, **3.05**, and **3.6** |
| **Logic Validation** | $\frac{1}{2.6} + \frac{1}{3.05} + \frac{1}{3.6} = 0.99$ ($\text{Result} < 1$). |
| **UI Result** | **Surebet Found!** ($\text{0.98\%}$ Profit) |
| **Stake Distribution (R$ 100.00)**| R$38.84, R$33.11 and R$28.05 |

---

### Scenario 3: Failure Validation (Business Rule)

| Attribute | Details |
| :--- | :--- |
| **Description** | Confirms the system prevents the user from proceeding in a non-profit scenario (Validation Obligation). |
| **Input Odds** | **1.68** and **1.90** |
| **Logic Validation** | $\frac{1}{1.68} + \frac{1}{1.90} = 1.11$ ($\text{Result} \ge 1$). |
| **UI Result** | **Not a Surebet.** |

---

## 🛠️ Implementation Details Summary

*This section is for collaborators and maintenance reference.*

The **"real-time"** functionality is achieved through the integration of **Laravel** and **Livewire**, which allows the logic processing to run on the *backend* (PHP) while instantly updating the *frontend* (Tailwind CSS) without requiring a page reload.

This approach ensures a highly reactive and performant user experience for a time-sensitive financial tool.

**Key Technologies:** Laravel, Livewire, and Tailwind CSS.
