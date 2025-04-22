# 🎓 Quiz Master - Modular Quiz Management System

Quiz Master is a robust full-stack **Flask** web application designed for educational institutions and e-learning platforms to create, manage, and evaluate quizzes with hierarchical structuring by **Subjects → Chapters → Quizzes → Questions**.

![Admin Dashboard](https://i.ibb.co/rGkL5YzR/Untitled-diagram-2025-04-22-071529.png)

---

## 🚀 Key Features

### 🛠 Admin Panel
- Full **CRUD operations**:
  - Subjects
  - Chapters
  - Quizzes
  - Questions
- Dynamic dashboard with:
  - Quiz statistics
  - Top user performance
- Modal-based entity creation (without page reloads)

### 👨‍🎓 User Portal
- Secure **Registration/Login**
- Explore subjects and quizzes
- Attempt quizzes with auto-scoring
- View **historical performance** and quiz attempts

---

## 🧰 Tech Stack

| Layer         | Technology                 |
|--------------|----------------------------|
| Backend       | Python + Flask             |
| ORM & DB      | SQLAlchemy + SQLite3       |
| Templates     | Jinja2, HTML5, CSS3        |
| Auth          | `werkzeug.security` (bcrypt) |
| UI Components | Bootstrap (modals/forms)   |

---

## 🧬 Database Schema Overview

- **User**
  - `id`, `username`, `password`, `is_admin`, `scores[]`
- **Subject**
  - `id`, `name`, `description`, `chapters[]`
- **Chapter**
  - `id`, `name`, `subject_id`, `quizzes[]`
- **Quiz**
  - `id`, `title`, `date_of_quiz`, `time_duration`, `chapter_id`, `questions[]`, `scores[]`
- **Question**
  - `id`, `question_statement`, `option1-4`, `correct_option`, `quiz_id`
- **Score**
  - `id`, `user_id`, `quiz_id`, `score`, `total_questions`, `timestamp`

> Relationships use SQLAlchemy backrefs with cascade deletes for integrity.

---

## 🖥️ System Flow

```plaintext
Admin:
  Create Subject → Add Chapter → Add Quiz → Add Questions
User:
  Browse → Attempt Quiz → View Results & Past Scores


⚙️ Installation Guide
🐍 Prerequisites
Python 3.8+

pip

📦 Setup
bash
Copy
Edit
# Clone the repo
git clone https://github.com/yourusername/quiz-master.git
cd quiz-master

# Optional: Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Initialize DB and admin user
python app.py
First run will automatically create an admin user with:

Username: admin

Password: 0000

🔐 Security
Password hashing: bcrypt via werkzeug.security

Session protection with Flask’s session object

Role-based access control (admin/user)

👨‍💻 Developer Notes
Structure
sql
Copy
Edit
📁 templates/
   ├─ admin/
   ├─ user/
📁 static/
app.py
README.md
requirements.txt
Development Server
bash
Copy
Edit
python app.py
Default runs at http://127.0.0.1:5000

🤝 Contributing
Fork the repo

Create a branch: git checkout -b feature-x

Commit changes: git commit -m 'Add feature x'

Push: git push origin feature-x

Open a Pull Request

🧪 Future Improvements
Quiz timer with countdown

Markdown or image support in questions

CSV import/export for bulk quiz management

REST API for external integrations

Analytics dashboard with charts

📃 License
MIT License © 2025 Your Name

Made with ❤️ using Flask.

yaml
Copy
Edit

---

Would you like me to save this as a file and send it to you?
