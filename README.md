# Flask Todo App — DevOps Edition

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://python.org) [![Flask](https://img.shields.io/badge/Flask-Web_App-black?logo=flask)](https://flask.palletsprojects.com) [![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker)](https://docker.com) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> A fully containerized full-stack web application built with Flask and Docker — deployable in any environment with a single command.

---

## Application Architecture

<svg width="900" height="340" viewBox="0 0 900 340" xmlns="http://www.w3.org/2000/svg" font-family="'Segoe UI', system-ui, sans-serif">
  <defs>
    <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse">
      <path d="M1 1L9 5L1 9" fill="none" stroke="#64748b" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
    <filter id="shadow" x="-10%" y="-10%" width="120%" height="130%">
      <feDropShadow dx="0" dy="2" stdDeviation="3" flood-color="#0001"/>
    </filter>
  </defs>

  <rect width="900" height="340" fill="#f8fafc" rx="16"/>

  <text x="450" y="38" text-anchor="middle" font-size="15" font-weight="700" fill="#0f172a" letter-spacing="-0.3">Application Architecture — flask-todo-devops</text>
  <text x="450" y="58" text-anchor="middle" font-size="11" fill="#94a3b8">Full-stack Flask Todo App — Containerized with Docker</text>

  <!-- Browser -->
  <g filter="url(#shadow)">
    <rect x="40" y="110" width="130" height="90" rx="12" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="40" y="110" width="130" height="8" rx="4" fill="#6366f1"/>
  <rect x="40" y="114" width="130" height="4" fill="#6366f1"/>
  <text x="105" y="150" text-anchor="middle" font-size="22">🌐</text>
  <text x="105" y="172" text-anchor="middle" font-size="12" font-weight="600" fill="#1e293b">Browser</text>
  <text x="105" y="188" text-anchor="middle" font-size="10" fill="#64748b">HTTP Request</text>

  <!-- Arrow -->
  <line x1="172" y1="155" x2="208" y2="155" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>
  <text x="190" y="147" text-anchor="middle" font-size="9" fill="#94a3b8">GET/POST</text>

  <!-- Flask App -->
  <g filter="url(#shadow)">
    <rect x="210" y="95" width="200" height="120" rx="12" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="210" y="95" width="200" height="8" rx="4" fill="#f97316"/>
  <rect x="210" y="99" width="200" height="4" fill="#f97316"/>
  <text x="310" y="135" text-anchor="middle" font-size="22">🐍</text>
  <text x="310" y="157" text-anchor="middle" font-size="12" font-weight="600" fill="#1e293b">Flask App (app.py)</text>
  <text x="310" y="173" text-anchor="middle" font-size="10" fill="#64748b">Routes: GET / POST /add</text>
  <text x="310" y="187" text-anchor="middle" font-size="10" fill="#64748b">Port: 5000</text>
  <text x="310" y="201" text-anchor="middle" font-size="10" fill="#64748b">Jinja2 templating</text>

  <!-- Arrow to template -->
  <line x1="412" y1="155" x2="448" y2="155" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>
  <text x="430" y="147" text-anchor="middle" font-size="9" fill="#94a3b8">renders</text>

  <!-- HTML Template -->
  <g filter="url(#shadow)">
    <rect x="450" y="110" width="140" height="90" rx="12" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="450" y="110" width="140" height="8" rx="4" fill="#ec4899"/>
  <rect x="450" y="114" width="140" height="4" fill="#ec4899"/>
  <text x="520" y="150" text-anchor="middle" font-size="22">🎨</text>
  <text x="520" y="172" text-anchor="middle" font-size="12" font-weight="600" fill="#1e293b">index.html</text>
  <text x="520" y="188" text-anchor="middle" font-size="10" fill="#64748b">Jinja2 template</text>

  <!-- Docker wrapper -->
  <rect x="190" y="75" width="440" height="165" rx="14" fill="none" stroke="#2496ed" stroke-width="2" stroke-dasharray="6 4"/>
  <text x="620" y="92" font-size="10" font-weight="700" fill="#2496ed">Docker Container</text>

  <!-- Arrow back -->
  <path d="M590 200 Q640 240 620 260 Q440 290 105 260 Q80 250 105 220" fill="none" stroke="#64748b" stroke-width="1.5" stroke-dasharray="4 3" marker-end="url(#arr)"/>
  <text x="390" y="290" text-anchor="middle" font-size="9" fill="#94a3b8">HTML response returned to browser</text>

  <!-- Bottom legend -->
  <rect x="40" y="255" width="820" height="60" rx="10" fill="#f1f5f9" stroke="#e2e8f0" stroke-width="1"/>
  <text x="60" y="275" font-size="11" font-weight="700" fill="#475569">Stack:</text>
  <rect x="100" y="263" width="8" height="8" rx="2" fill="#f97316"/>
  <text x="114" y="273" font-size="11" fill="#475569">Python / Flask</text>
  <rect x="210" y="263" width="8" height="8" rx="2" fill="#ec4899"/>
  <text x="224" y="273" font-size="11" fill="#475569">HTML / Jinja2</text>
  <rect x="320" y="263" width="8" height="8" rx="2" fill="#2496ed"/>
  <text x="334" y="273" font-size="11" fill="#475569">Docker</text>
  <text x="60" y="300" font-size="10" fill="#94a3b8">Run: docker build -t flask-todo-app .   →   docker run -p 5000:5000 flask-todo-app   →   open localhost:5000</text>
</svg>

---

## Project Structure

<svg width="900" height="320" viewBox="0 0 900 320" xmlns="http://www.w3.org/2000/svg" font-family="'Segoe UI', system-ui, sans-serif">
  <defs>
    <filter id="shadow" x="-10%" y="-10%" width="120%" height="130%">
      <feDropShadow dx="0" dy="2" stdDeviation="3" flood-color="#0001"/>
    </filter>
  </defs>

  <rect width="900" height="320" fill="#0f172a" rx="16"/>
  <text x="450" y="38" text-anchor="middle" font-size="15" font-weight="700" fill="#f1f5f9" letter-spacing="-0.3">Project Structure — flask-todo-devops</text>

  <!-- File tree -->
  <rect x="40" y="60" width="280" height="220" rx="10" fill="#1e293b" stroke="#334155" stroke-width="1"/>
  <text x="60" y="88" font-size="12" font-weight="700" fill="#94a3b8" font-family="monospace">flask-todo-devops/</text>

  <line x1="72" y1="100" x2="72" y2="240" stroke="#334155" stroke-width="1"/>

  <line x1="72" y1="112" x2="88" y2="112" stroke="#334155" stroke-width="1"/>
  <text x="94" y="117" font-size="11" fill="#7dd3fc" font-family="monospace">📁 templates/</text>

  <line x1="100" y1="124" x2="100" y2="136" stroke="#334155" stroke-width="1"/>
  <line x1="100" y1="136" x2="116" y2="136" stroke="#334155" stroke-width="1"/>
  <text x="122" y="141" font-size="11" fill="#f9a8d4" font-family="monospace">index.html</text>

  <line x1="72" y1="155" x2="88" y2="155" stroke="#334155" stroke-width="1"/>
  <text x="94" y="160" font-size="11" fill="#86efac" font-family="monospace">🐍 app.py</text>

  <line x1="72" y1="178" x2="88" y2="178" stroke="#334155" stroke-width="1"/>
  <text x="94" y="183" font-size="11" fill="#7dd3fc" font-family="monospace">🐳 dockerfile</text>

  <line x1="72" y1="200" x2="88" y2="200" stroke="#334155" stroke-width="1"/>
  <text x="94" y="205" font-size="11" fill="#c4b5fd" font-family="monospace">📄 requirements.txt</text>

  <!-- Detail cards -->
  <rect x="360" y="60" width="240" height="80" rx="8" fill="#1e293b" stroke="#f9a8d4" stroke-width="1.5"/>
  <text x="376" y="82" font-size="11" font-weight="700" fill="#f9a8d4">🎨 templates/index.html</text>
  <text x="376" y="98" font-size="10" fill="#94a3b8">Jinja2 HTML template for the</text>
  <text x="376" y="112" font-size="10" fill="#94a3b8">Todo UI. Renders todo list.</text>
  <text x="376" y="128" font-size="10" fill="#64748b">{{ todos }}  ·  form action="/add"</text>

  <rect x="360" y="155" width="240" height="80" rx="8" fill="#1e293b" stroke="#86efac" stroke-width="1.5"/>
  <text x="376" y="177" font-size="11" font-weight="700" fill="#86efac">🐍 app.py</text>
  <text x="376" y="193" font-size="10" fill="#94a3b8">Flask routes. GET / renders todos.</text>
  <text x="376" y="207" font-size="10" fill="#94a3b8">POST /add adds new item.</text>
  <text x="376" y="223" font-size="10" fill="#64748b">app.run(host="0.0.0.0", port=5000)</text>

  <rect x="620" y="60" width="240" height="80" rx="8" fill="#1e293b" stroke="#7dd3fc" stroke-width="1.5"/>
  <text x="636" y="82" font-size="11" font-weight="700" fill="#7dd3fc">🐳 dockerfile</text>
  <text x="636" y="98" font-size="10" fill="#94a3b8">Containerizes the Flask app.</text>
  <text x="636" y="112" font-size="10" fill="#94a3b8">Installs deps, runs on port 5000.</text>
  <text x="636" y="128" font-size="10" fill="#64748b">FROM python → pip install → CMD</text>

  <rect x="620" y="155" width="240" height="80" rx="8" fill="#1e293b" stroke="#c4b5fd" stroke-width="1.5"/>
  <text x="636" y="177" font-size="11" font-weight="700" fill="#c4b5fd">📄 requirements.txt</text>
  <text x="636" y="193" font-size="10" fill="#94a3b8">Python package dependencies.</text>
  <text x="636" y="207" font-size="10" fill="#94a3b8">Installed inside the container.</text>
  <text x="636" y="223" font-size="10" fill="#64748b">flask, jinja2, ...</text>

  <!-- Bottom bar -->
  <rect x="40" y="268" width="820" height="32" rx="8" fill="#1e293b" stroke="#334155" stroke-width="1"/>
  <text x="450" y="288" text-anchor="middle" font-size="10" fill="#64748b">Python  ·  Flask  ·  Jinja2  ·  Docker  ·  Port 5000  ·  Full-stack web application</text>
</svg>

---

## What I Built

I built a Todo web application from scratch and wrapped it in a complete DevOps delivery workflow. The focus was not just on the app itself, but on how it is packaged and deployed — containerizing it with Docker so it runs identically on any machine, in any environment.

This project demonstrates my ability to:
- Develop a **full-stack web application** with Python, Flask, and HTML/Jinja2
- Containerize an application using **Docker** with a clean, minimal Dockerfile
- Structure a project for real-world deployment pipelines
- Manage Python environments and dependencies professionally

---

## Tech Stack

| Technology | Role |
|---|---|
| Python | Backend application runtime |
| Flask | Web framework and routing |
| HTML / Jinja2 | Server-side templating |
| Docker | Containerization and portability |

---

## Features

- Add and view todo items through a clean web interface
- Full-stack Python application with server-side rendered HTML
- Fully containerized — runs identically on any machine with Docker
- Structured for easy extension with a database or CI/CD pipeline

---

## File Structure

```
flask-todo-devops/
├── templates/
│   └── index.html        # Jinja2 frontend template
├── app.py                # Flask routes and application logic
├── dockerfile            # Docker container definition
└── requirements.txt      # Python dependencies
```

---

## Run It Locally

**With Docker:**
```bash
git clone https://github.com/Aijazkhan123/flask-todo-devops.git
cd flask-todo-devops
docker build -t flask-todo-app .
docker run -p 5000:5000 flask-todo-app
```
Open **http://localhost:5000**

**Without Docker:**
```bash
pip install -r requirements.txt
python app.py
```

---

## Planned Improvements

- [ ] Add PostgreSQL database for persistent storage
- [ ] Implement GitHub Actions CI/CD pipeline
- [ ] Deploy to AWS ECS or Azure App Service
- [ ] Add unit and integration tests with pytest

---

## Skills Demonstrated

`Python` · `Flask` · `Docker` · `Jinja2 Templating` · `REST API Design` · `Containerization` · `Full-Stack Development`
