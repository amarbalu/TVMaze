
# TV Shows Web Application

This project is a full-stack application that allows users to list and view details of TV shows. It consists of:
- **Backend**: A Java-based REST API to fetch and process TV show details using the TVMaze API.
- **Frontend**: A React-based UI to display TV shows and their details.
- **Docker**: Both backend and frontend are containerized and managed using `docker-compose`.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Technologies Used](#technologies-used)
3. [Setup and Running the Application](#setup-and-running-the-application)
4. [API Endpoints Documentation](#api-endpoints-documentation)
5. [Assumptions and Decisions](#assumptions-and-decisions)
6. [Notes](#notes)

---

## Project Overview

The application provides the following features:
1. Consume a provided `tvtitles.txt` file, process the titles, and fetch show details from the [TVMaze API](http://api.tvmaze.com/).
2. List all TV shows.
3. Display detailed information about individual TV shows.

---

## Technologies Used

- **Backend**:
  - Java 8+
  - Spring Boot
  - (Optional) H2 in-memory database
- **Frontend**:
  - React
  - CSS framework (e.g., Material-UI or Bootstrap)
- **Other Tools**:
  - Docker
  - Docker Compose

---

## Setup and Running the Application

### Prerequisites
1. Docker and Docker Compose installed on your system.
2. Java 8+ and Node.js (optional for local setup).

### Steps to Run the Application
1. Clone or extract the repository:
   ```bash
   git clone <repository-link>
   cd <project-directory>
   ```

2. Start the application using Docker Compose:
   ```bash
   docker-compose up --build
   ```

3. Access the application:
   - **Frontend**: [http://localhost:3000](http://localhost:3000)
   - **Backend**: [http://localhost:8080](http://localhost:8080)

### Local Development (Without Docker)
1. **Backend**:
   - Navigate to the `backend` directory and build the application:
     ```bash
     cd backend
     ./mvnw spring-boot:run
     ```
   - Backend will be accessible at `http://localhost:8080`.

2. **Frontend**:
   - Navigate to the `frontend` directory and start the React app:
     ```bash
     cd frontend
     npm install
     npm start
     ```
   - Frontend will be accessible at `http://localhost:3000`.

---

## API Endpoints Documentation

| Method | Endpoint                 | Description                         |
|--------|---------------------------|-------------------------------------|
| GET    | `/api/shows`             | Fetch the list of TV shows          |
| POST   | `/api/shows`             | Add TV show titles from `tvtitles.txt` |
| GET    | `/api/shows/{id}`        | Fetch details of a specific TV show |

### Sample API Usage

#### 1. Fetch All TV Shows
**Request**:
```bash
GET /api/shows
```

**Response**:
```json
[
  {
    "id": 1,
    "name": "Breaking Bad",
    "genre": "Drama",
    "network": "AMC",
    "status": "Ended",
    "schedule": {
      "time": "21:00",
      "days": ["Sunday"]
    },
    "summary": "A high school chemistry teacher turned methamphetamine producer."
  }
]
```

#### 2. Fetch TV Show Details
**Request**:
```bash
GET /api/shows/1
```

**Response**:
```json
{
  "id": 1,
  "name": "Breaking Bad",
  "genre": "Drama",
  "network": "AMC",
  "status": "Ended",
  "schedule": {
    "time": "21:00",
    "days": ["Sunday"]
  },
  "summary": "A high school chemistry teacher turned methamphetamine producer."
}
```

---

## Assumptions and Decisions

1. **TV Show Titles**: Titles are processed from the `tvtitles.txt` file using the TVMaze API.
2. **Data Persistence**: The backend uses an in-memory data structure (or H2 database) for simplicity. No external database was configured.
3. **UI Design**: Styled with a CSS framework (e.g., Material-UI or Bootstrap) for a simple and responsive design.
4. **Docker Ports**:
   - Backend: `8080`
   - Frontend: `3000`
5. **TVMaze API Integration**:
   - `/singlesearch/shows?q={title}` is used to fetch TV show details.

---

## Notes

1. The application is designed as a minimal proof-of-concept for listing and displaying TV shows.
2. Future enhancements can include:
   - Persistent database support (e.g., MySQL/PostgreSQL).
   - Authentication and role-based access control.
   - Enhanced UI with additional filters or search functionality.
3. Make sure to whitelist `http://localhost:3000` for CORS in the backend if testing locally.

---

## Author

- **Name**: [Your Name]
- **GitHub**: [Your GitHub Link]
- **Email**: [Your Email]

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
