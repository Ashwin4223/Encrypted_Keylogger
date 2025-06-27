# 🔐 Encrypted Keylogger PoC with Simulated Remote Server
ElevateLabs Internship Project

## 🎯 Objective
This Proof of Concept (PoC) captures user keystrokes, encrypts the log securely using symmetric encryption, and simulates exfiltrating the data to a remote server (locally hosted using Flask). Designed **strictly for ethical and educational use only**.

---

## ⚙️ Features
- 🎹 **Keylogging**: Records keypresses in real-time.
- 🛑 **Kill-Switch**: Press `Esc` to stop the keylogger instantly.
- 🔐 **Encryption**: Encrypts the logs using Fernet (AES-based symmetric encryption).
- 🚀 **Simulated Upload**: Press `F12` to trigger upload of encrypted logs to the server.
- 📡 **Server Endpoint**: A Flask-based local server receives and stores the logs in the `uploads/` folder.

---

## 📂 Project Structure
```
.
├── keylogger.py      # Main keylogger script with encryption & upload logic
├── server.py         # Flask server to receive encrypted logs
├── secret.key        # Symmetric key used for Fernet encryption (auto-generated)
├── keylogs.txt       # Unencrypted keystroke logs
├── encrypted_log.txt # Encrypted keystroke logs
└── uploads/          # Directory where the server stores uploaded files
```

---

## 🛠️ Setup & Run

### 🔧 1. Install Dependencies
Make sure you have Python 3 installed. Then run:
```bash
pip install pynput cryptography flask requests
```

### 🚀 2. Start the Flask Server
This simulates the remote server receiving the logs.
```bash
python server.py
```

Server will run on `http://localhost:5000`.

### 🎯 3. Run the Keylogger
This starts listening for keystrokes:
```bash
python keylogger.py
```

- Press `Esc` to terminate logging.
- Press `F12` to **encrypt and upload** the current logs to the server.

---

## 🔍 Example Interaction
- Typing `hello world` will be logged.
- Pressing `F12` will:
  - Encrypt `keylogs.txt` to `encrypted_log.txt`
  - Upload it to `http://localhost:5000/upload`

Server response:  
```
"File received!"
```

---

## ⚠️ Disclaimer & Ethical Use
> This tool is developed **purely for learning and demonstration purposes**.  
> **Do not deploy or use this in real-world systems without clear, informed consent** from all participants.  
> Misuse may be **illegal and unethical**. Stay on the white-hat side! 🕵️‍♂️🛡️

