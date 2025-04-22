# 🧠 Quiz Master - MAD 1

**Quiz Master** is a powerful, full-stack Flask web application that allows administrators to create and manage subject-wise quizzes while enabling users (students) to take them, track their scores, and view performance insights. It's a modular quiz platform ideal for academic institutions and online learning environments.

![Quiz Master Banner](https://imgur.com/y3hKf1K.png)

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
erDiagram
    User ||--o{ Score : has
    Quiz ||--o{ Question : includes
    Subject ||--o{ Chapter : contains
    Chapter ||--o{ Quiz : contains
    Quiz ||--o{ Score : evaluated_in
    User {
        int id
        string username
        string password
        string full_name
        string qualification
        string dob
        bool is_admin
    }
    Subject {
        int id
        string name
        text description
    }
    Chapter {
        int id
        string name
        text description
        int subject_id
    }
    Quiz {
        int id
        string title
        string date_of_quiz
        string time_duration
        text remarks
        int chapter_id
    }
    Question {
        int id
        text question_statement
        text option1
        text option2
        text option3
        text option4
        int correct_option
        int quiz_id
    }
    Score {
        int id
        int user_id
        int quiz_id
        int score
        int total_questions
        datetime timestamp
    }
# MAD_1

## 📈 Dashboard Preview (Admin)

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
