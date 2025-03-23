# Flask Auth using MySQL Database

<p><strong>This project implements a User Authentication System using MySQL Database connectivity and Flask.</strong></p>

---

## 🚀 Features
- Implemented user authentication/registration form using Flask and the database.  
   - **New Users**: Register using the signup button.  
   - **Existing Users**: Login with their credentials.  
- Inside, users can update their personal details and reset their passwords.
- Users can view their grades but cannot edit them personally.
- Built a **responsive frontend** for user interactions using Bootstrap.
- Implemented backend flask connectivity with MySQL database.

---

## 🖼️ Preview
![Home Page](./preview/home.png)

---

## 📜 License  

Flask Auth is open-source and released under the **MIT License**.  
See the [LICENSE](./LICENSE) file for more details.

---

## 🛠️ Get Started

### 1️⃣ Clone the Repository
```sh
git clone "https://github.com/QwertyFusion/Database-Management-Using-Flask"
cd Database-Management-Using-Flask
```

### 2️⃣ Backend Setup (Flask)

#### Create and Activate Virtual Environment (venv)
```sh
python -m venv venv  # Create virtual environment
source venv/bin/activate  # MacOS/Linux
venv\Scripts\activate  # Windows
```

#### Install Dependencies
```sh
pip install -r requirements.txt
```

### 3️⃣ Database Setup (MySQL and MySQL Workbench)

#### Install MySQL Server and MySQL Workbench from official websites
```yaml
MySQL Server Download Link: https://dev.mysql.com/downloads/installer/
MySQL Workbench Download Link: https://dev.mysql.com/downloads/workbench/
```

#### In MySQL Workbench, create `user_management` database and use it
```sql
CREATE DATABASE user_management;
USE user_management;
```

#### In MySQL Workbench, create `user` table and `grades` table and use it 
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE grades (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    subject VARCHAR(100) NOT NULL,
    grade DECIMAL(5, 2) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);
```

#### In MySQL Workbench, insert into `grades` table after creating account using frontend. Do this before logging in.
```sql
INSERT INTO grades (user_id, subject, grade) VALUES (1, '<SUBJECT_NAME>', <GRADE>);
```

### 4️⃣ Environment Variables

#### Create `.env` similar to `.env.example` for Flask Backend connectivity with your MySQL Database server:
```env
SECRET_KEY=mysecretkey # Keep this same, no need to change or delete
MYSQL_HOST=YOUR_MYSQL_SERVER_HOST
MYSQL_USER=root
MYSQL_PASSWORD=YOUR_MYSQL_SERVER_PASSWORD
MYSQL_DB=user_management # Your Database name
```

### 5️⃣ Run the Project

#### Start the Flask Backend
```bash
python app.py  # Ensure the virtual environment is activated
```

Now, open your browser and go to **http://127.0.0.1:5000** to start using Flask Auth! 🚀

---

## 🛠 Tools Used  

<ol>
  <li>Visual Studio Code</li>
  <li>HTML</li>
  <li>CSS</li>
  <li>Bootstrap</li>
  <li>Flask</li>
  <li>MySQL</li>
  <li>MySQL Workbench</li>
  <li>Git & GitHub (Version Control)</li>
</ol>

---

## 🔗 Link to Tools  

<p align="left">
<a href="https://code.visualstudio.com" target="_blank" rel="noreferrer">
  <img src="https://www.vectorlogo.zone/logos/visualstudio_code/visualstudio_code-icon.svg" alt="Visual Studio Code" width="40" height="40"/>
</a>&emsp;
<a href="https://developer.mozilla.org/en-US/docs/Web/HTML" target="_blank" rel="noreferrer">
  <img src="https://cdn.iconscout.com/icon/free/png-256/free-html-5-logo-icon-download-in-svg-png-gif-file-formats--programming-langugae-language-pack-logos-icons-1175208.png?f=webp&w=256" alt="HTML" width="40" height="40"/>
</a>&emsp;
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS" target="_blank" rel="noreferrer">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/CSS3_logo.svg/2048px-CSS3_logo.svg.png" alt="CSS" width="40" height="40"/>
</a>&emsp;
<a href="https://getbootstrap.com" target="_blank" rel="noreferrer">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b2/Bootstrap_logo.svg/1280px-Bootstrap_logo.svg.png" alt="Bootstrap" width="40"/>
</a>&emsp;
<a href="https://flask.palletsprojects.com/" target="_blank" rel="noreferrer">
  <img src="https://play-lh.googleusercontent.com/ekpyJiZppMBBxCR5hva9Zz1pr3MYlFP-vWTYR3eIU7HOMAmg3jCJengHJ1GFgFMyyYc" alt="Flask" width="40" height="40"/>
</a>&emsp;
<a href="https://dev.mysql.com/downloads/installer/" target="_blank" rel="noreferrer">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Antu_mysql-workbench.svg/800px-Antu_mysql-workbench.svg.png" alt="MySQL" width="40" height="40"/>
</a>&emsp;
<a href="https://dev.mysql.com/downloads/workbench/" target="_blank" rel="noreferrer">
  <img src="https://img.utdstc.com/icon/f6f/11c/f6f11c75fda63dd454fa5db9610a77cfd6752be4db11010f2e4252551a4abccd:200" alt="MySQL Workbench" width="40" height="40"/>
</a>&emsp;
<a href="https://git-scm.com/" target="_blank" rel="noreferrer">
  <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="Git" width="40" height="40"/>
</a>&emsp;
<a href="https://github.com/" target="_blank" rel="noreferrer">
  <img src="https://uxwing.com/wp-content/themes/uxwing/download/brands-and-social-media/github-white-icon.png" alt="GitHub" width="40" height="40"/>
</a>
</p>

---

## 👨‍💻 Developer  

<ul>
  <li><a href="https://github.com/QwertyFusion">[@QwertyFusion]</a></li>
</ul>
