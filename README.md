<div align="center">

# 📹 PeerConnect — Real-Time P2P Video Calling Platform

<img src="https://img.shields.io/badge/WebRTC-brightgreen?style=for-the-badge&logo=webrtc&logoColor=white"/>
<img src="https://img.shields.io/badge/Socket.io-010101?style=for-the-badge&logo=socket.io&logoColor=white"/>
<img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white"/>
<img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB"/>

### ⚡ Browser-to-Browser. No plugins. No middlemen. Just pure P2P.

[🚀 Live Demo](#) · [🐛 Report Bug](https://github.com/ASHISH-SAINI78021/videoCallingApp/issues) · [⭐ Star this repo](https://github.com/ASHISH-SAINI78021/videoCallingApp)

</div>

---

## 🎯 What is PeerConnect?

**PeerConnect** is a real-time peer-to-peer video calling platform built from scratch using **WebRTC** — enabling direct, low-latency browser-to-browser communication without any third-party media servers.

No Zoom SDK. No Twilio. Just raw WebRTC, a custom signaling server, and sub-second video calls. 🔥

---

## ✨ Features

| Feature | Description |
|---|---|
| 📡 **P2P Video Calling** | Direct browser-to-browser streaming via WebRTC |
| 🏠 **Room-Based Sessions** | Secure 1-to-1 video rooms with unique room IDs |
| ⚡ **Sub-Second Latency** | Optimized ICE candidate exchange for near-instant calls |
| 🔁 **Custom Signaling Server** | Built with Socket.io for offer/answer/ICE exchange |
| 🌐 **Cross-Network Support** | Stable connections across different networks via ICE |
| 🎙️ **Audio + Video Streaming** | Real-time media tracks with clean track management |

---

## 🏗️ Architecture

```
Caller                  Signaling Server            Callee
  │                     (Socket.io)                   │
  │──── Create Room ──────────►│                      │
  │                            │◄──── Join Room ───── │
  │◄─────────────── Room Ready ┤                      │
  │                            │                      │
  │──── SDP Offer ────────────►│──── SDP Offer ──────►│
  │◄─── SDP Answer ────────────│◄─── SDP Answer ───── │
  │                            │                      │
  │◄════ ICE Candidates ═══════════════════════════► │
  │                            │                      │
  │◄════════════ Direct P2P WebRTC Stream ══════════► │
  │                       (No Server)                 │
```

> 🔑 Once connected, **all media flows directly peer-to-peer** — the signaling server steps out completely.

---

## 🛠️ Tech Stack

```
Frontend          Backend           Protocol
─────────         ────────          ────────
React.js    +    Node.js      +    WebRTC
                 Express.js        Socket.io (Signaling)
                                   ICE / STUN
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js v16+
- npm or yarn

### Installation

```bash
# Clone the repo
git clone https://github.com/ASHISH-SAINI78021/videoCallingApp.git

# Navigate to project
cd videoCallingApp

# Install server dependencies
cd server && npm install

# Install client dependencies
cd ../client && npm install
```

### Running Locally

```bash
# Start the signaling server
cd server
npm start          # Runs on http://localhost:5000

# Start the React client
cd client
npm start          # Runs on http://localhost:3000
```

> Open two browser tabs → Create a room in one → Join via room ID in the other → 🎉

---

## 🔬 How It Works

### 1️⃣ Signaling (Socket.io)
Before peers can talk directly, they need to exchange metadata — **SDP offers/answers** and **ICE candidates**. This is handled by a lightweight Node.js + Socket.io signaling server.

### 2️⃣ WebRTC Handshake
```
Peer A creates RTCPeerConnection
     → generates SDP Offer
     → sends via signaling server
Peer B receives Offer
     → generates SDP Answer
     → sends back via signaling server
Both peers set local/remote descriptions ✅
```

### 3️⃣ ICE Candidate Exchange
ICE candidates are network paths. Both peers exchange them via the signaling server to find the **best possible direct route** — even across NATs and firewalls.

### 4️⃣ P2P Stream
Once ICE negotiation completes, **media flows directly** between browsers. The server is completely out of the loop. 🎯

---

## 📁 Project Structure

```
videoCallingApp/
├── client/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Room.jsx          # Video call UI
│   │   │   └── Lobby.jsx         # Room creation/join
│   │   ├── context/
│   │   │   └── SocketContext.js  # Socket.io context
│   │   └── App.jsx
│   └── package.json
│
├── server/
│   ├── index.js                  # Signaling server
│   └── package.json
│
└── README.md
```

---

## 🧠 Key Concepts Demonstrated

- ✅ **WebRTC** — RTCPeerConnection, MediaStream, SDP
- ✅ **Signaling** — Custom Socket.io signaling server from scratch
- ✅ **ICE Framework** — STUN servers, candidate gathering & exchange
- ✅ **NAT Traversal** — Stable connections across different networks
- ✅ **Real-time Events** — Bidirectional socket communication
- ✅ **React Hooks** — useRef for video streams, useEffect for socket lifecycle

---

## 🔮 Future Improvements

- [ ] 🔇 Mute / Camera toggle controls
- [ ] 👥 Multi-party calls (SFU architecture)
- [ ] 💬 In-call chat via data channels
- [ ] 🔐 End-to-end encrypted rooms
- [ ] 📱 Mobile responsive UI
- [ ] 🖥️ Screen sharing support
- [ ] 🎙️ TURN server integration for strict NAT environments

---

## 👨‍💻 Author

**Ashish Saini**

[![GitHub](https://img.shields.io/badge/GitHub-ASHISH--SAINI78021-black?style=flat-square&logo=github)](https://github.com/ASHISH-SAINI78021)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ashish%20Saini-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/ashish-saini-a641902b3)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-orange?style=flat-square&logo=google-chrome)](https://ashish-portfolio.ashu78021.workers.dev/)

---

<div align="center">

### ⭐ If this project helped you, please consider giving it a star!

*Built with ❤️ and a deep hatred for Zoom's pricing*

</div>
