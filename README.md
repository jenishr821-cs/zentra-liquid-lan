# 🌐 Zentra Liquid LAN

> ### 🧊 A private, real-time LAN chat experience with a premium Liquid Glass interface.

**Zentra Liquid LAN** is a lightweight, private messaging application designed for devices connected to the **same local network**.

It combines real-time WebSocket communication with a modern **Liquid Glass UI**, private messaging, file sharing, live server monitoring, responsive mobile support, and customizable visual themes.

No cloud messaging service is required.

Your messages stay on your local network. 🔒

---

## ✨ Features

### 💬 Real-Time Messaging

* ⚡ Real-time WebSocket communication
* 👥 Global LAN Lounge
* 🔐 Private 1-to-1 conversations
* ✍️ Live typing indicators
* 🔔 Message notifications
* 🟢 Online user presence
* 💾 Message history using SQLite
* 😀 Large emoji collection

### 🧊 Liquid Glass UI

* ✨ Premium frosted-glass interface
* 🌈 Animated multi-color background
* 🎨 Multiple visual themes
* 💨 Adjustable glass blur
* 🔍 Adjustable glass clarity
* 🌊 Adjustable background animation
* 🏝️ Dynamic Island-style status panel
* 📱 Responsive desktop and mobile interface

### 👤 User Experience

* 🧑 Custom username
* 🔄 Persistent browser session
* 🟢 Automatic reconnect
* 👤 User avatar support
* 🔤 Automatic first-letter avatar
* 🔊 Notification sound controls
* 🌙 Dark Glass mode

### 📁 File Sharing

* 📤 Upload files directly through the chat
* 🖼️ Image previews
* 📥 File downloads
* 📊 Upload progress indicator
* 📦 Maximum file size: **25 MB per file**

### 📊 Live Server Monitor

Zentra includes a real-time server monitoring panel:

| Monitor            | Description                  |
| ------------------ | ---------------------------- |
| 👥 Connected Users | Currently connected clients  |
| 🟢 WebSockets      | Active WebSocket connections |
| 📡 Network Traffic | Current server traffic       |
| 💾 RAM Usage       | Server memory usage          |
| ⚡ Messages/sec     | Messaging activity           |
| 📁 Active Uploads  | Current file uploads         |
| 💽 Storage         | Shared file storage usage    |
| 🖥️ CPU            | Server CPU usage             |
| 🟠 Load Warning    | Server load condition        |

### 🛡️ Server Protection

* 🔐 Password-protected server startup
* 👥 Maximum **50 simultaneous users**
* 🚫 Duplicate username protection
* 📦 File upload size protection
* 🔒 LAN-focused architecture
* 🧹 Runtime files excluded from Git

---

# 🔐 Server Password

Zentra can require a **server password before the chat server starts**.

When the server is launched, the administrator must enter the configured password before Zentra becomes available.

Example:

```text
🔐 Enter Zentra Server Password:
```

Only after successful authentication will the server continue starting.

> ⚠️ **Important:** Never publish your actual server password in this README or upload it to GitHub.

Keep passwords private and use environment variables or another secure configuration method when deploying outside a trusted LAN.

---

# 🖥️ Requirements

### Software

* 🐍 Python 3.10+
* 🌐 Modern web browser
* 📡 Local Wi-Fi/Ethernet network

### Supported Devices

| Platform            | Support |
| ------------------- | ------- |
| 🪟 Windows          | ✅       |
| 🍎 macOS            | ✅       |
| 🐧 Linux            | ✅       |
| 🤖 Android          | ✅       |
| 📱 iOS              | ✅       |
| 💻 Desktop browsers | ✅       |
| 🌐 Mobile browsers  | ✅       |

---

# 🚀 Installation

## 1️⃣ Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/zentra-liquid-lan.git
```

Enter the project:

```bash
cd zentra-liquid-lan
```

---

## 2️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

If your system uses `python3`:

```bash
pip3 install -r requirements.txt
```

---

## 3️⃣ Start Zentra

```bash
python server.py
```

The server will ask for the configured server password if password protection is enabled.

After successful authentication, Zentra will start on:

```text
http://127.0.0.1:8000
```

---

# 📡 Connect Other Devices

All devices must be connected to the **same Wi-Fi/LAN network**.

Find the computer's local IP address.

### Windows

```powershell
ipconfig
```

Look for:

```text
IPv4 Address
```

For example:

```text
192.168.1.25
```

Then open Zentra from another device:

```text
http://192.168.1.25:8000
```

### 📱 Android / iPhone

Connect the phone to the same Wi-Fi as the Zentra server.

Open:

```text
http://YOUR-PC-IP:8000
```

Example:

```text
http://192.168.1.25:8000
```

🎉 The phone can now join the Zentra LAN.

---

# 🏗️ Project Structure

```text
Zentra/
│
├── 📄 server.py
├── 📄 requirements.txt
├── 📄 README.md
├── 📄 LICENSE
├── 📄 .gitignore
│
├── 📁 static/
│   └── 📄 index.html
│
└── 📁 shared_files/
    └── 📄 .gitkeep
```

### `server.py`

The main backend responsible for:

* WebSocket connections
* User presence
* Messaging
* Private messages
* File uploads
* SQLite storage
* Server statistics
* Connection/session handling
* Server limits

### `static/index.html`

The main Zentra interface containing:

* HTML
* CSS
* JavaScript
* Liquid Glass UI
* Responsive layout
* WebSocket client
* Emoji system
* Theme controls
* Mobile interface

The frontend is intentionally kept in a **single HTML file** for easy deployment and modification.

---

# 🧠 Architecture

```text
                 ┌─────────────────────┐
                 │   Zentra Server     │
                 │     Python          │
                 │     aiohttp         │
                 └──────────┬──────────┘
                            │
              ┌─────────────┼─────────────┐
              │             │             │
              ▼             ▼             ▼
         💻 Laptop       📱 Android      🍎 iPhone
         WebSocket       WebSocket       WebSocket
              │             │             │
              └─────────────┼─────────────┘
                            │
                       🏠 Local LAN
```

Zentra is designed around a **local-network architecture**, allowing connected devices to communicate through the same private server.

---

# 👥 User Capacity

The server currently supports a maximum of:

```text
👥 50 simultaneous users
```

The limit is enforced by the server rather than being only a visual UI value.

Actual performance depends on:

* 💻 Server hardware
* 📡 Wi-Fi speed
* 🌐 Network quality
* 💬 Message activity
* 📁 File transfers
* 💾 Storage performance

---

# 📱 Mobile Experience

Zentra is optimized for mobile browsers.

### Android & iOS features

* 👆 Touch-friendly controls
* ↔️ Swipe sidebar
* ◀️ Back/close panel
* ⌨️ Mobile keyboard-safe composer
* 📐 Dynamic viewport support
* 🏠 Safe-area support
* 🔘 Large touch targets
* 📱 Responsive layouts

The interface is designed to remain usable when the mobile keyboard is open.

---

# 🎨 Customization

Zentra includes several visual controls.

### 🧊 Liquid Glass

Adjust:

```text
Blur
Glass Clarity
Background Motion
```

### 🌈 Background

Customize multiple colors:

```text
Color 1
Color 2
Color 3
```

The colors smoothly blend into the animated background.

### 🎨 Themes

Available themes include:

* 💎 Crystal
* 💜 Lavender
* 🌿 Mint
* 🍑 Peach
* ☁️ Sky
* 🌌 Aurora

---

# 🔒 Privacy

Zentra is designed for **private local-network communication**.

Messages and files are handled by the local Zentra server instead of requiring a cloud messaging platform.

However:

> ⚠️ Zentra should not be considered an enterprise-grade secure messenger. Network administrators and devices on the same network may still have visibility into network activity depending on the environment.

For sensitive deployments, additional encryption and authentication should be implemented.

---

# 🛠️ Troubleshooting

### ❌ Other devices cannot connect

Check:

1. Both devices are on the same Wi-Fi/LAN.
2. Zentra server is running.
3. Windows Firewall allows Python/server port `8000`.
4. You are using the server PC's LAN IP.

Example:

```text
http://192.168.1.25:8000
```

---

### ❌ Port 8000 is already being used

Find the process using the port and stop it, or change the configured Zentra port in `server.py`.

---

### ❌ Mobile keyboard hides the message box

Refresh the page and ensure you're using a modern browser.

Zentra uses mobile viewport and safe-area handling to keep the composer visible.

---

# 📸 Screenshots

Add your project screenshots here:

```text
docs/
├── desktop.png
├── mobile.png
├── liquid-glass.png
├── private-chat.png
└── server-monitor.png
```

Then add them to this README:

```markdown
![Zentra Desktop](docs/desktop.png)

![Zentra Mobile](docs/mobile.png)
```

---

# 🚀 Future Improvements

Possible future versions may include:

* 🔐 End-to-end encryption
* 👥 User groups
* 🎙️ Voice messaging
* 📹 Video calls
* 🗂️ File management
* 🔑 User authentication
* 🧑‍💼 Admin dashboard
* 📊 Advanced analytics
* 🗄️ PostgreSQL support
* ⚡ Redis-based scaling
* 🌍 Optional internet deployment
* 🔔 Advanced notification system

---

# 🤝 Contributing

Contributions, suggestions and improvements are welcome.

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature/new-feature
```

3. Make your changes
4. Commit them

```bash
git commit -m "Add new feature"
```

5. Push the branch

```bash
git push origin feature/new-feature
```

6. Open a Pull Request 🚀

---

# 📜 License

Copyright © 2026 **Jenish Rathod**

This project is provided for educational and personal development purposes.

See the `LICENSE` file for the complete license terms.

---

# 👨‍💻 Author

### Jenish Rathod

🎓 B.Sc. IT Student
🔐 Cybersecurity Enthusiast
💻 Developer
🌐 Networking & Linux Learner

---

## ⭐ Support the Project

If you find **Zentra Liquid LAN** interesting:

⭐ Star the repository
🍴 Fork the project
🐛 Report bugs
💡 Suggest improvements
📢 Share the project

---

<div align="center">

### 🧊 Zentra Liquid LAN

**Private • Local • Real-Time • Liquid**

Made with ❤️ and ☕ by **Jenish Rathod**

**© 2026 Jenish Rathod**

</div>
