# 🧠 Quiz Master - MAD 1

**Quiz Master** is a powerful, full-stack Flask web application that allows administrators to create and manage subject-wise quizzes while enabling users (students) to take them, track their scores, and view performance insights. It's a modular quiz platform ideal for academic institutions and online learning environments.

---

## 🚀 Features

### 👨‍🏫 Admin Capabilities
- Full CRUD for:
  - Subjects
  - Chapters within subjects
  - Quizzes within chapters
  - Questions within quizzes
- Dashboard overview with statistics
- View and analyze scores of all users

### 👩‍🎓 User Features
- Register & login securely
- Browse subjects and quizzes
- Attempt quizzes and view results
- Track previous scores and quiz attempts

### 🔐 Authentication
- Passwords are securely hashed using `werkzeug.security`
- Admin and user roles with session-based access control

---

## 🛠️ Tech Stack

| Layer         | Technology                            |
|---------------|----------------------------------------|
| Backend       | Python, Flask                         |
| Database      | SQLite3, SQLAlchemy ORM               |
| Frontend      | HTML, CSS (Jinja templates)           |
| Security      | Werkzeug Password Hashing             |

---

## 🧬 Database Schema

The system is built on a relational schema as follows:

```mermaid

# MAD_1

## 📈 Dashboard Preview (Admin)
https://i.ibb.co/rGkL5YzR/Untitled-diagram-2025-04-22-071529.png
+-------------------------------------------------------------+
|                   Admin Dashboard                           |
+----------------+----------------+----------------+----------+
| Subjects Count | Chapters Count | Quizzes Count  | Questions|
+----------------+----------------+----------------+----------+
|       8        |       24       |       42       |   210    |
+-------------------------------------------------------------+
| Top Users (Avg. Score %)                                     |
| - John Doe (82.4%)                                           |
| - Jane Smith (79.3%)                                         |
+-------------------------------------------------------------+

## 📋 How to Run

# Clone the repository
git clone https://github.com/yourusername/quiz-master.git
cd quiz-master

# Set up virtual environment (optional)
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
