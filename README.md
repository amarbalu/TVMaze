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

Frontend: http://localhost:3000

Backend: http://localhost:8080

🔧 Local Development (Without Docker)
Backend

cd tvshow-backend
./mvnw spring-boot:run
Backend will run on http://localhost:8080

Frontend

cd tvshow-frontend
npm install
npm start
Frontend will run on http://localhost:3000

📘 API Endpoints
Method	Endpoint	Description
GET	/api/shows	Fetch the list of TV shows
POST	/api/shows	Load TV shows from tvtitles.txt
GET	/api/shows/{id}	Fetch detailed info of a TV show

🧠 Assumptions & Design Decisions
TV show titles are read from tvtitles.txt

Data stored in H2 in-memory DB for simplicity

CORS enabled for local frontend testing

API integration with /singlesearch/shows?q={title} from TVMaze

Frontend designed with responsive CSS framework

🌱 Future Enhancements
Switch to persistent DB (MySQL/PostgreSQL)

Add user authentication and roles

Implement search, sort, and filter features

Improve UI/UX with advanced styling

👨‍💻 Author
Amar Balu

💼 GitHub

✍️ Medium

If you find this project helpful, feel free to ⭐ the repo and follow for updates!
