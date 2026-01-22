# 🛡️ Mini-SOAR: Automated Identity Threat Detection System

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Prototype-orange.svg)

**Mini-SOAR** is a lightweight Security Orchestration, Automation, and Response (SOAR) engine built in Python. It simulates a Security Operations Center (SOC) environment by ingesting synthetic authentication logs, detecting advanced identity-based attacks, and executing automated mitigation strategies to neutralize threats in real-time.

## 🚀 Project Overview

In modern cybersecurity, identity is the new perimeter. Traditional static firewalls often fail to detect behavioral anomalies like "MFA Fatigue" or "Impossible Travel." This project bridges that gap by using statistical analysis and geokinetic calculations to identify and block threats automatically.

### Key Features
* **Synthetic Log Generator:** Uses `Faker` to create realistic enterprise authentication traffic (Login Success/Fail, MFA Request/Deny).
* **Impossible Travel Detection:** Calculates the velocity between logins using the **Haversine Formula** to detect physically impossible movement (>500 mph).
* **MFA Fatigue Detection:** Identifies "MFA Bombing" attacks by analyzing the sequence of *Deny* vs. *Approve* events.
* **Password Spraying Detection:** Detects low-and-slow attacks by analyzing unique username targets per source IP.
* **Automated Response:** Simulates "Firewall Block" and "Session Revocation" actions based on detection triggers.

## 📊 Visuals & Results

The system successfully identifies simultaneous attack vectors. Below is the generated attack timeline showing the distinct patterns of Password Spraying (vertical wall) vs. Impossible Travel (green gap).

### Mitigation Output
The system generates an automated audit log upon detection:
| Threat Detected | Action Taken | Outcome |
| :--- | :--- | :--- |
| **Password Spraying** | 🔥 BLOCK IP (Firewall) | Success |
| **MFA Fatigue** | 🔒 LOCK ACCOUNT | Success |
| **Impossible Travel** | 🚫 REVOKE SESSION | Success |

## 🛠️ Installation & Usage

You can run this project locally or in Google Colab.

### Option 1: Run Locally
1.  **Clone the repository**
    ```bash
    git clone [https://github.com/yourusername/Mini-SOAR.git](https://github.com/yourusername/Mini-SOAR.git)
    cd Mini-SOAR
    ```
2.  **Install Dependencies**
    ```bash
    pip install pandas numpy faker matplotlib seaborn
    ```
3.  **Run the Engine**
    ```bash
    python mini_soar.py
    ```

### Option 2: Run in Google Colab
Simply copy the code from `mini_soar.py` into a new Google Colab notebook. Ensure you add `!pip install Faker` at the top of the first cell.
