# 🔐 Password Strength Checker & Threat Detector

A Python-based desktop security application that evaluates password strength and checks whether a password has appeared in known data breaches.

The application combines local password-strength analysis with the **Have I Been Pwned (HIBP) Pwned Passwords API** to provide users with security-focused feedback before using a password.

## 🚀 Features

### 🔑 Password Strength Analysis

The application evaluates passwords based on multiple security characteristics:

- Password length
- Lowercase letters
- Uppercase letters
- Numbers
- Special characters
- Common password detection
- Repeated character detection
- Keyboard and sequential patterns
- Word + digits patterns
- Additional scoring for longer passwords

The password receives a score from **0 to 100** and is classified as:

- Very Weak
- Weak
- Moderate
- Strong
- Very Strong

### 🛡️ Data Breach Detection

The application checks whether the entered password has appeared in known data breaches using the **Have I Been Pwned Pwned Passwords API**.

If a breach is found, the application displays:

- Number of times the password was found in breach data
- A warning advising the user not to use the password

If no breach is found, the application displays:

> SAFE - No breach record found.

### 🔒 Privacy-Preserving Password Check

The complete password is **not sent to the breach-checking API**.

The application:

1. Creates a SHA-1 hash of the password locally.
2. Sends only the first 5 characters of the hash to the API.
3. Receives matching hash suffixes.
4. Compares the remaining hash locally.
5. Determines whether the password appears in breach data.

This allows the password itself to remain on the user's machine during the breach check.

### 🖥️ Graphical User Interface

The application provides a simple Tkinter-based interface with:

- Password input field
- Show/hide password option
- Real-time strength score
- Visual strength progress bar
- Security recommendations
- Threat/breach checking
- Network error handling

---

## 🛠️ Technologies Used

- **Python**
- **Tkinter** - Graphical user interface
- **Regular Expressions (`re`)** - Password pattern analysis
- **SHA-1 (`hashlib`)** - Password hashing
- **urllib** - API communication
- **Threading** - Non-blocking API requests
- **Have I Been Pwned Pwned Passwords API** - Data breach checking

---

## 📂 Project Structure

```text
Password-Strength-Checker-Threat-Detector/
│
├── password_threat_detector.py
├── README.md
├── requirements.txt
├── .gitignore
│
└── screenshots/
    ├── strength-check.png
    └── threat-detected.png
