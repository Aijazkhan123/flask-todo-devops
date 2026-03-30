# ✅ Flask Todo App — DevOps Edition

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-Web%20Framework-lightgrey?logo=flask)](https://flask.palletsprojects.com)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker)](https://docker.com)
[![HTML](https://img.shields.io/badge/Frontend-HTML%2FCSS-E34F26?logo=html5)](https://developer.mozilla.org/en-US/docs/Web/HTML)

A full-stack To-Do web application built with Python Flask and Jinja2 HTML templates — containerized with Docker and designed with DevOps practices in mind. Create, view, and manage tasks through a clean browser-based UI.

---

## 🏗️ Architecture Diagram

```
┌──────────────────────────────────────────────────────────────────────┐
│                    APPLICATION ARCHITECTURE                          │
│                                                                      │
│   🖥️ Browser / Client                                                │
│       │                                                              │
│       │  HTTP Request (GET / POST)                                   │
│       ▼                                                              │
│  ┌─────────────────────────────────────────────────────────────┐    │
│  │                  🐳 Docker Container                         │    │
│  │                                                             │    │
│  │  ┌───────────────────────────────────────────────────────┐  │    │
│  │  │              🐍 Flask Application (app.py)            │  │    │
│  │  │                                                       │  │    │
│  │  │   Routes:                                             │  │    │
│  │  │   GET  /          → Render todo list                  │  │    │
│  │  │   POST /add       → Add new task                      │  │    │
│  │  │   GET  /delete/id → Remove a task                     │  │    │
│  │  │                                                       │  │    │
│  │  │   ┌─────────────────┐   renders   ┌───────────────┐  │  │    │
│  │  │   │  In-Memory /    │ ──────────► │  templates/   │  │  │    │
│  │  │   │  SQLite Store   │             │  index.html   │  │  │    │
│  │  │   └─────────────────┘             │  (Jinja2)     │  │  │    │
│  │  │                                   └───────────────┘  │  │    │
│  │  └───────────────────────────────────────────────────────┘  │    │
│  │                                                             │    │
│  │  Base Image: python:3.x-slim                                │    │
│  │  Exposed Port: 5000                                         │    │
│  └─────────────────────────────────────────────────────────────┘    │
│                                                                      │
│       │  HTTP Response (rendered HTML page)                         │
│       ▼                                                              │
│   🖥️ Browser displays the Todo list                                  │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│                       FILE STRUCTURE MAP                             │
│                                                                      │
│   flask-todo-devops/                                                 │
│   │                                                                  │
│   ├── app.py          ← Flask routes & task logic                   │
│   ├── dockerfile      ← Builds and packages the container           │
│   ├── requirements.txt← Python dependencies (Flask)                 │
│   └── templates/                                                     │
│       └── index.html  ← Jinja2 HTML template for the UI             │
└──────────────────────────────────────────────────────────────────────┘
```

---

## 📁 Project Structure

```
flask-todo-devops/
├── templates/
│   └── index.html        # Jinja2 HTML UI template
├── app.py                # Flask application — routes and logic
├── dockerfile            # Docker container definition
└── requirements.txt      # Python package dependencies
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Backend | Python + Flask | Web server and routing |
| Frontend | HTML + Jinja2 | Server-side rendered UI |
| Containerization | Docker | Package and run the app |
| Dependencies | pip / requirements.txt | Manage Python packages |

---

## ⚡ Getting Started

### Run with Docker

```bash
# Clone the repository
git clone https://github.com/Aijazkhan123/flask-todo-devops.git
cd flask-todo-devops

# Build the Docker image
docker build -t flask-todo-devops .

# Run the container
docker run -p 5000:5000 flask-todo-devops
```

Open your browser at: **http://localhost:5000**

### Run Locally (without Docker)

```bash
# Install Python dependencies
pip install -r requirements.txt

# Start the Flask development server
python app.py
```

---

## 🖥️ Features

- ➕ **Add tasks** via a web form
- 📋 **View all tasks** in a clean list UI
- 🗑️ **Delete tasks** individually
- 🐳 Fully **Dockerized** for easy portability
- 🌐 Server-side rendered HTML with **Jinja2 templates**

---

## 🧠 What I Learned

- Building a full-stack web app with Flask and Jinja2 templates
- Rendering dynamic content from Python to HTML
- Containerizing a Python web app with Docker
- Structuring a clean, deployable DevOps-ready project

---

## 🗺️ Planned Improvements

- [ ] Persist tasks with SQLite or PostgreSQL database
- [ ] Add task completion/done status toggle
- [ ] Add GitHub Actions CI/CD pipeline for auto-deployment
- [ ] Deploy to cloud (AWS, Railway, Render, etc.)
- [ ] Add user authentication

---

## 📜 License

MIT License — free to fork and build upon.

---

`Python` · `Flask` · `Jinja2` · `HTML` · `Docker` · `DevOps` · `Full Stack`
