# 🔒 Secure File Sharing Server & Client (TLS 1.3)

This project is a **secure file sharing system** developed in **C++** using **POSIX sockets** and **OpenSSL (TLS 1.3)**.  
It demonstrates secure client–server communication with encryption, authentication, and safe file transfer.

---

## 🧠 Project Overview
The server accepts TLS 1.3-secured TCP connections. Authenticated clients can:
- List files on the server  
- Download files  
- Upload files  

All actions are encrypted and logged.

Built as part of **Wipro Training – Capstone Project (Assignment 4)**.

---

## ⚙️ Features
- ✅ Client–Server communication over TCP sockets  
- ✅ TLS 1.3 encryption (OpenSSL)  
- ✅ User authentication (admin/user1/user2)  
- ✅ File upload & download with progress bars  
- ✅ Auto-create folders (server/client/logs)  
- ✅ Event logging (`server.log`, `security.log`)  
- ✅ Works on Linux / WSL (Ubuntu)

---

## 🧩 Project Structure
```bash
file-sharing-app/
├── src/
│   ├── server.cpp
│   ├── client.cpp
│   ├── tls_wrapper.h
│   ├── common.h
├── server_files/         # files available to download
├── server_uploads/       # uploaded by clients
├── client_downloads/     # downloaded by clients
├── logs/                 # server & security logs
├── Makefile
├── generate_certs.sh
└── README.md
```

---

## 🧰 Technologies Used
- **Language:** C++  
- **Networking:** POSIX Sockets (TCP/IP)  
- **Encryption:** OpenSSL (TLS 1.3, RSA 2048-bit)  
- **Build Tool:** Makefile  
- **Platform:** Linux / WSL (Ubuntu)

---

## 🚀 Setup & Run

### 1️⃣ Generate TLS Certificates
```bash
chmod +x generate_certs.sh
./generate_certs.sh
```

### 2️⃣ Build the Project
```bash
make clean && make
```

### 3️⃣ Run the Server
```bash
./server
```
Expected output:
```bash
=== Secure File Sharing Server (TLS 1.3) ===
🚀 Server started on port 9090
```

### 4️⃣ Run the Client
In another terminal:
```bash
./client
```
Login with:
```bash
Username: admin
Password: admin123
```

---

## 🖥️ Demo Workflow
1. Login as an existing user (e.g., `admin`)  
2. View the file list from the server  
3. Download and upload files securely  
4. Check the real-time logs:
   ```bash
   tail -f logs/server.log logs/security.log
   ```
5. Verify TLS encryption:
   ```bash
   openssl s_client -connect 127.0.0.1:9090 -tls1_3
   ```
   Expected output:
   ```bash
   Protocol  : TLSv1.3
   Cipher    : TLS_AES_256_GCM_SHA384
   ```

---

## 👥 Default User Accounts
| Username | Password  |
|-----------|-----------|
| admin     | admin123  |
| user1     | password1 |
| user2     | password2 |

---

## 📜 Example Log Entries

**server.log**
```bash
Mon Nov  3 20:49:11 2025
 - admin downloaded config.ini (27 bytes)
Mon Nov  3 20:50:22 2025
 - admin uploaded test_upload.txt (28 bytes)
```

**security.log**
```bash
Mon Nov  3 20:29:51 2025
 - User authenticated: admin
Mon Nov  3 21:01:23 2025
 - Auth failed (attempt 2)
```

---

## 👤 Author
**Ayush Ray**  
Developed under **Wipro TalentNext Capstone Project 2025**  
📧 ayushray489@gmail.com
🔗 [GitHub Profile](https://github.com/Ayushray489)

---

## 🏁 License
This project is intended for educational and demonstration purposes only.  
All rights reserved © 2025.

---

## 🧠 Optional – Add GitHub Badges
You can add these just below the title for a professional look:
```markdown
![C++](https://img.shields.io/badge/Language-C++-blue)
![OpenSSL](https://img.shields.io/badge/Security-TLS%201.3-green)
![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20WSL-lightgrey)
![Status](https://img.shields.io/badge/Status-Final%20Submission-success)
```


