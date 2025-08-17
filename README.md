# Library Management System

**DMDD‑Group‑10**  
An advanced Library Management System with a dedicated UI, built as part of the Data Management & Database Design (DMDD) course, where the backend framework primarily redirected queries to code logic implemented entirely in .sql files, leveraging Azure SQL Edge with complex triggers, stored procedures, user-defined functions, and views.

---

## Table of Contents

1. [Overview](#overview)  
2. [Features](#features)  
3. [Tech Stack](#tech-stack)  
4. [Repository Structure](#repository-structure)  
5. [Getting Started](#getting-started)  
    - [Prerequisites](#prerequisites)  
    - [Installation](#installation)  
    - [Running the App](#running-the-app)  
6. [API Endpoints](#api-endpoints)  
7. [Contributing](#contributing)  
8. [License](#license)  
9. [Contact](#contact)  

---

## Overview

This project is a Library Management System that allows librarians to:

- Maintain an inventory of books  
- Register and manage library members  
- Record book borrow/return transactions  
- Search and filter books by title, author, ISBN, or genre  

It is structured as a separate **backend** (REST API) and **frontend** (static web UI) for clear separation of concerns.

---

## Features

- **Book Management**  
  - Add new books  
  - Edit book details  
  - Delete books  
  - View all books  

- **User Management**  
  - Register new members  
  - Edit member profiles  
  - Deactivate/reactivate members  

- **Transactions**  
  - Borrow books (creates a loan record)  
  - Return books (updates loan record, tracks due dates & fines)  
  - View borrowing history  

- **Search & Filtering**  
  - Full‑text search on titles and authors  
  - Filter by genre, availability, publication year  

---

## Tech Stack

- **Backend:** Python (Flask)  
- **Frontend:** HTML5, CSS3, JavaScript (Vanilla ES6)  
- **Database:** SQLite (via SQLAlchemy ORM)  
- **Dependencies:** See `requirements.txt`  

---

## Repository Structure

```
Library_Management_System/
├── backend/                # Flask REST API
│   ├── app.py              # Main application entrypoint
│   ├── models.py           # SQLAlchemy ORM models
│   ├── routes.py           # API endpoint definitions
│   ├── config.py           # Configuration (DB URI, etc.)
│   └── …                   # Additional modules
├── frontend/               # Static web UI
│   ├── index.html          # Main dashboard
│   ├── styles.css          # Global styles
│   ├── scripts.js          # Client‑side logic & API calls
│   └── assets/             # Images, icons, etc.
├── P5/                     # Reports & deliverables (presentations, PDFs)
├── .gitignore              # Patterns to ignore in git
├── requirements.txt        # Python dependencies
└── README.md               # This file
```

---

## Getting Started

### Prerequisites

- Python 3.7 or higher  
- pip (comes with Python)  
- (Optional) virtualenv or venv for isolated environments  

### Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/SachinVishaul007/Library_Management_System.git
   cd Library_Management_System
   ```

2. **Set up a Python virtual environment**  
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate   # On Windows: .venv\Scripts\activate
   ```

3. **Install backend dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

---

## Running the App

1. **Start the backend server**  
   ```bash
   cd backend
   export FLASK_APP=app.py
   flask run
   ```
   By default, the API will be available at `http://127.0.0.1:5000/`.

2. **Open the frontend**  
   Simply open `frontend/index.html` in your browser (no build step required).  
   The UI will interact with the Flask API for data.

---

## API Endpoints

| Method | Endpoint            | Description                         |
|--------|---------------------|-------------------------------------|
| GET    | `/api/books`        | List all books                      |
| GET    | `/api/books/<id>`   | Get details for a single book       |
| POST   | `/api/books`        | Add a new book                      |
| PUT    | `/api/books/<id>`   | Update an existing book             |
| DELETE | `/api/books/<id>`   | Remove a book from inventory        |
| GET    | `/api/members`      | List all library members            |
| POST   | `/api/members`      | Register a new member               |
| POST   | `/api/borrow`       | Record a book borrow transaction    |
| POST   | `/api/return`       | Record a book return transaction    |

*(Adjust paths and payloads as implemented in `routes.py`.)*

---

## Contributing

1. Fork the repo  
2. Create a feature branch (`git checkout -b feature/YourFeature`)  
3. Commit your changes (`git commit -m "Add some feature"`)  
4. Push to your branch (`git push origin feature/YourFeature`)  
5. Open a Pull Request  

Please adhere to the existing code style and include tests for any new functionality.

---

