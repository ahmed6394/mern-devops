# MERN Task App - DevOps Demo

A full-stack task management application built with the MERN stack (MongoDB, Express, React, Node.js) and containerized for DevOps deployment.

## 🚀 Features

- **Task Management**: Create, read, and manage tasks
- **Modern UI**: React 19 frontend with Tailwind CSS styling
- **RESTful API**: Express backend with MongoDB integration
- **Docker Support**: Containerized services for easy deployment
- **CI/CD Ready**: Jenkins pipeline included for automation

## 📋 Tech Stack

- **Frontend**: React 19, Vite, Tailwind CSS
- **Backend**: Node.js, Express.js
- **Database**: MongoDB 6.0
- **DevOps**: Docker, Docker Compose, Jenkins

## 🏗️ Project Structure

```
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable React components
│   │   ├── services/       # API service layer
│   │   └── utils/          # Utility functions
│   └── Dockerfile
├── server/                 # Node.js/Express backend
│   ├── controllers/        # Route handlers
│   ├── models/             # Mongoose schemas
│   ├── routes/             # API routes
│   └── Dockerfile
├── docker-compose.yaml     # Multi-container orchestration
└── Jenkinsfile            # CI/CD pipeline
```

## 🛠️ Quick Start

### Prerequisites
- Docker & Docker Compose
- Or: Node.js (v16+), MongoDB

### Using Docker Compose (Recommended)

```bash
# Start all services
docker-compose up -d

# Frontend available at: http://localhost:5173
# Backend API available at: http://localhost:5000/api
```

### Local Development

**Backend:**
```bash
cd server
npm install
npm run dev
```

**Frontend:**
```bash
cd client
npm install
npm run dev
```

## 📚 API Endpoints

- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create a new task
- `GET /api/tasks/:id` - Get task by ID
- `PUT /api/tasks/:id` - Update task
- `DELETE /api/tasks/:id` - Delete task

## 🧹 Code Quality

```bash
# Lint code
npm run lint

# Fix linting issues
npm run lint:fix

# Format code
npm run format
```

## 📦 Environment Variables

Create a `.env` file in the `server` directory:

```
MONGODB_URI=mongodb://mongo:27017/taskapp
PORT=5000
NODE_ENV=development
```

## 🐳 Docker Services

| Service | Port | Description |
|---------|------|-------------|
| Frontend | 5173 | React Vite dev server |
| Backend | 5000 | Express API server |
| MongoDB | (internal) | Database service |


