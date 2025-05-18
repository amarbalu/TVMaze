# 📺 TV Shows Web Application

A full-stack web application to list and view TV shows using the [TVMaze API](https://www.tvmaze.com/api). Built with **Spring Boot** (Java), **React**, and **Docker**.

---

## 🚀 Features
- Reads `tvtitles.txt` and fetches show details via TVMaze API
- Lists all shows with pagination and display cards
- View detailed info about a single show
- Containerized with Docker and Docker Compose

---

## 🛠 Tech Stack

**Frontend**
- React.js
- Material-UI / Bootstrap (choose based on what you used)

**Backend**
- Java 8+, Spring Boot
- H2 In-Memory DB

**DevOps**
- Docker
- Docker Compose

---

## 📦 Setup Instructions

### ▶️ Run with Docker
```bash
git clone https://github.com/amarbalu/TVMaze.git
cd TVMaze

# Clone frontend and backend
git clone https://github.com/amarbalu/tvshow-frontend.git
git clone https://github.com/amarbalu/tvshow-backend.git

# Run
docker-compose up --build
