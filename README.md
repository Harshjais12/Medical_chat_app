# Medical_chat_app

# 🏥 Medical Chat App

A real-time medical chat application built with a **client-server architecture**, enabling patients and healthcare professionals to communicate securely and efficiently. Built using **JavaScript**, **Node.js**, **Socket.IO**, **React**, and **CSS**.

---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the App](#running-the-app)
- [How It Works](#how-it-works)
- [Environment Variables](#environment-variables)
- [Contributing](#contributing)
- [License](#license)

---

## 📖 About the Project

The **Medical Chat App** is a full-stack web application designed to facilitate real-time communication between patients and medical professionals (doctors, nurses, consultants). It provides a seamless, user-friendly chat interface that bridges the gap between patients and healthcare providers, allowing for quick consultations without requiring physical visits.

The application follows a classic **client-server model**:
- The **client** is the frontend interface users interact with in their browser.
- The **server** handles all communication logic, message routing, and API requests.

---

## ✨ Features

- 💬 **Real-time Messaging** — Instant, bidirectional communication using WebSockets (Socket.IO).
- 🏥 **Medical Context** — Chat interface tailored for patient-doctor or patient-support communication.
- 📱 **Responsive UI** — Clean and accessible design that works across desktops and mobile devices.
- 🔌 **Client-Server Architecture** — Decoupled frontend and backend for scalability and maintainability.
- 🚀 **Fast & Lightweight** — Minimal dependencies for quick load times.

---

## 🛠 Tech Stack

### Frontend (Client)
| Technology | Purpose |
|---|---|
| **React.js / JavaScript** | UI components and interactivity |
| **CSS** | Styling and responsive layout |
| **HTML** | Markup structure |
| **Socket.IO Client** | Real-time WebSocket communication |

### Backend (Server)
| Technology | Purpose |
|---|---|
| **Node.js** | JavaScript runtime environment |
| **Express.js** | Web framework for REST API and serving routes |
| **Socket.IO** | WebSocket server for real-time events |

---

## 📁 Project Structure

```
Medical_chat_app/
│
├── client/                  # Frontend React application
│   ├── public/              # Static public assets (HTML entry point, icons)
│   ├── src/                 # React source files
│   │   ├── components/      # Reusable UI components (ChatBox, MessageBubble, etc.)
│   │   ├── pages/           # Page-level components (Home, Chat room)
│   │   ├── App.js           # Root component
│   │   └── index.js         # React app entry point
│   ├── package.json         # Client-side dependencies
│   └── ...
│
├── server/                  # Backend Node.js application
│   ├── index.js             # Main server entry point
│   ├── routes/              # API route handlers
│   ├── socket/              # Socket.IO event handlers
│   ├── package.json         # Server-side dependencies
│   └── ...
│
└── README.md                # Project documentation
```

---

## 🚀 Getting Started

Follow these steps to run the project locally on your machine.

### Prerequisites

Make sure you have the following installed before you begin:

- **Node.js** (v14 or higher) — [Download here](https://nodejs.org/)
- **npm** (comes with Node.js) or **yarn**
- **Git** — [Download here](https://git-scm.com/)

You can verify your installations by running:

```bash
node -v
npm -v
git --version
```

---

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/Harshjais12/Medical_chat_app.git
cd Medical_chat_app
```

**2. Install server dependencies**

```bash
cd server
npm install
```

**3. Install client dependencies**

```bash
cd ../client
npm install
```

---

### Running the App

You need to run both the **server** and **client** in separate terminal windows.

**Terminal 1 — Start the backend server:**

```bash
cd server
npm start
```

The server will start on `http://localhost:5000` (or the port defined in your config).

**Terminal 2 — Start the frontend client:**

```bash
cd client
npm start
```

The React app will open automatically at `http://localhost:3000`.

> ✅ Make sure the server is running **before** you start the client, so the socket connection can be established properly.

---

## ⚙️ How It Works

### 1. User Opens the App
When a user visits the app in their browser, the React frontend loads and establishes a **WebSocket connection** with the Node.js server via **Socket.IO**.

### 2. Joining a Chat Room
Users can enter their name/role (e.g., Patient, Doctor) and join a chat room. This information is sent to the server, which registers the user and notifies other connected users.

### 3. Sending Messages
When a user sends a message:
- The client emits a socket event (e.g., `send_message`) to the server.
- The server receives the event and **broadcasts** it to the other participants in the room.
- The recipient's client picks up the incoming event and **renders the new message** in real time.

### 4. Real-Time Updates
All chat activity (messages, user joins/leaves) is reflected instantly across all connected clients without any need to refresh the page — thanks to **WebSocket (Socket.IO)** technology.

---

## 🔐 Environment Variables

If the project uses environment variables, create a `.env` file inside the `server/` directory:

```
PORT=5000
CLIENT_URL=http://localhost:3000
```

> ⚠️ Never commit your `.env` file to version control. Add it to `.gitignore`.

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Make your changes and **commit**: `git commit -m "Add: your feature description"`
4. **Push** to your branch: `git push origin feature/your-feature-name`
5. Open a **Pull Request**

Please make sure your code is clean, well-commented, and does not break existing functionality.

---

## 👨‍💻 Author

**Harsh Jaiswal**
- GitHub: [@Harshjais12](https://github.com/Harshjais12)

---

## 📄 License

This project is open source. Feel free to use, modify, and distribute it with proper attribution.

---

> 💡 **Disclaimer:** This application is intended for educational and demonstration purposes. It is not a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare provider for medical concerns.
