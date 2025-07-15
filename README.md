# Password Manager
---
the live web tool: https://password-manager-snqf.onrender.com/
----
## 1. Project Overview

This project is a Secure Password Manager Web Application built using Flask and SQLite with encryption handled by cryptography.
It allows users to register and securely store passwords for multiple sites, protected by a master password and encrypted using industry-standard algorithms.

---
## 2. Key Features

- User registration and login with hashed master passwords
- AES encryption (via Fernet) for stored passwords
- Password entries tied to user accounts
- Reveal passwords after re-authenticating with master password
- Secure session management
- SQLite database storage for users and entries
- Dockerized for easy deployment
  
  ---
  
  ## 3. Technology Stack

| Component           | Technology                  |
|---------------------|-----------------------------|
| Backend Framework   | Flask                       |
| Database            | SQLite (via SQLAlchemy)     |
| Encryption          | Python cryptography library |
| Password Hashing    | Werkzeug Security           |
| Containerization    | Docker                      |
| Deployment Target   | Render.com (optional)       |

---

## 4. How It Works
- Users register with a username and master password. The master password is hashed with salt and stored.
- When logging in, the master password is verified, and a key is derived using PBKDF2 and the user’s unique salt.
- Password entries (site, username, password) are encrypted with the derived key and saved.
- To reveal a password, the user must enter their master password again to decrypt the stored password.
- Sessions track logged-in users, securing access to entries.

---

