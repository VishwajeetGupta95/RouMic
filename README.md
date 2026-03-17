# 🎤 RouMic

**RouMic** is a real-time web application where users join a virtual street and get a **random chance to perform live** using webcam streaming.

It combines **live streaming, randomness, and audience interaction** — like a digital open mic powered by chance.

---

## 🚀 Features (MVP)

* 👥 Join a public “Virtual Street” room
* 🎲 Join a performer queue
* 🔀 Random performer selection every 2 minutes
* 🎥 Live video streaming using WebRTC
* 💬 Real-time chat with WebSocket
* 👀 Multiple viewers watching one performer

---

## 🏗️ Tech Stack

### Backend

* Java 17
* Spring Boot
* Spring WebSocket

### Frontend

* HTML
* CSS
* JavaScript

### Streaming

* WebRTC (Peer-to-Peer)

---

## 📁 Project Structure

```
roumic/
├── backend/   → signaling (WebSocket)
├── frontend/  → UI + WebRTC
└── README.md
```

---

## ⚙️ How It Works

1. Users open the app and enter a username
2. They join the **Virtual Street room**
3. Users click **Join Queue**
4. Backend stores them in a queue
5. Every 120 seconds:

   * A random performer is selected
   * The performer gets the stage
6. The performer starts webcam streaming
7. Viewers watch and interact via chat

---

## 🔌 WebSocket Endpoints

```
/ws                → WebSocket connection
/topic/chat        → Chat messages
/topic/queue       → Queue updates
/topic/stage       → Active performer updates
/topic/signal      → WebRTC signaling
```

---

## 🎥 WebRTC Flow

1. Performer starts camera using `getUserMedia()`
2. Creates WebRTC offer
3. Sends offer via WebSocket
4. Viewers send answer
5. ICE candidates exchanged
6. Stream starts

---

## 🛠️ Setup Instructions

### 1. Clone the repository

```
git clone https://github.com/your-username/roumic.git
cd roumic
```

---

### 2. Run Backend

```
cd backend
mvn spring-boot:run
```

Server runs at:

```
http://localhost:8080
```

---

### 3. Run Frontend

Open:

```
frontend/index.html
```

Or use a live server extension.

---

## 🧪 Testing the App

* Open multiple browser tabs
* Enter different usernames
* Join queue from different tabs
* Wait for random performer selection
* Start camera from selected user
* Others watch the stream

---

## ⚠️ Limitations (MVP)

* Uses **peer-to-peer WebRTC** (not scalable)
* No authentication system
* No persistent database
* No moderation or reporting

---

## 🔮 Future Improvements

* Media server integration (LiveKit / Janus)
* User authentication (JWT)
* Redis-based distributed queue
* Payment & tipping system
* AI moderation
* Mobile support

---

## 🎯 Goal of the Project

RouMic is designed as a **learning + portfolio project** to explore:

* real-time systems
* WebSocket communication
* WebRTC streaming
* backend architecture with Spring Boot

---

## 🤝 Contributing

Contributions are welcome. Feel free to fork and improve the project.

---

## 📄 License

This project is open-source and available under the MIT License.

---

## 💡 Tagline

**“Get the Mic. Anytime.”**
