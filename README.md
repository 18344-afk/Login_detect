# 🔐 Secure Login System (with Intrusion Detection)

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python)
![GUI](https://img.shields.io/badge/Interface-Tkinter-green?style=flat-square)
![Security](https://img.shields.io/badge/Security-SHA256-red?style=flat-square)

A Python-based graphical login interface that demonstrates essential security concepts. This project implements password hashing, session locking, and a visual intrusion detection log to monitor authentication attempts in real-time.

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Key Features](#-key-features)
- [Authentication Logic](#-authentication-logic)
- [Installation](#-installation)

---

## 📖 Overview

This application serves as an educational example of how to secure user authentication. unlike basic login scripts, this tool prevents "Brute Force" attacks by locking accounts after repeated failures and stores passwords securely using SHA-256 hashing rather than plain text.

It features a split-screen interface:
* **Left Panel:** User interaction (Login form).
* **Right Panel:** Administrator view (Real-time security logs).

## 🌟 Key Features

* **🛡️ SHA-256 Hashing:** Passwords are hashed before comparison; plain text passwords are never stored.
* **🚫 Brute Force Protection:** Automatically locks the account for 30 seconds after 3 failed attempts.
* **👁️ Visual Logging:** A live "Intrusion Detection" panel showing successful logins (Green), failed attempts (Yellow), and lockouts (Red).
* **🔒 Account Locking:** Enforces a "cool-down" period to prevent automated dictionary attacks.

---

## 🧠 Authentication Logic

The system follows a strict validation flow to ensure security:

```bash
graph TD
    A[User Clicks Login] --> B{Account Locked?}
    B -- Yes --> C[Show Error & Block]
    B -- No --> D[Hash Input Password]
    D --> E{Hash Matches DB?}
    
    E -- Yes --> F[Login Success]
    F --> G[Reset Fail Count]
    
    E -- No --> H[Increment Fail Count]
    H --> I{Count >= 3?}
    I -- Yes --> J[Lock Account (30s)]
    I -- No --> K[Show Warning]
```

## ⚡ Installation

### Prerequisites
* **Python 3.x**: Ensure Python is installed on your system.
* **Tkinter**: This usually comes pre-installed with Python. If you are on Linux and get an error, you may need to install it (e.g., `sudo apt-get install python3-tk`).

### Steps
1. **Download:** Save the script as `login_dec.py`.
2. **Run:** Open your terminal or command prompt and execute:
   ```bash
   python login_dec.py
   ```
   
