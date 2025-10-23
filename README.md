# 🧑‍💻 ECHO- Express Authentication & Post System

A simple **Node.js + Express.js** web app with **JWT-based authentication**, **bcrypt password hashing**, and **EJS frontend**.  
Users can register, log in, create posts, like/unlike posts, and edit their own posts — all securely managed with JWT tokens stored in cookies.

---

## 🚀 Features

✅ User Registration with password hashing  
✅ User Login with JWT token authentication  
✅ Protected routes using middleware  
✅ Create, edit, and delete posts  
✅ Like / Unlike posts  
✅ Profile page showing user details & posts  
✅ Secure password storage using **bcrypt**  
✅ Token-based authentication using **jsonwebtoken**

---

## 🧰 Tech Stack

| Layer | Technology |
|--------|-------------|
| **Backend** | Node.js, Express.js |
| **Frontend** | EJS (Embedded JavaScript Templates) |
| **Database** | MongoDB (Mongoose ODM) |
| **Authentication** | JWT (jsonwebtoken), bcrypt |
| **Middleware** | cookie-parser, express.json, express.urlencoded |

---

## 📁 Folder Structure

├── app.js
├── models/
│ ├── user.js
│ └── post.js
├── views/
│ ├── index.ejs
│ ├── login.ejs
│ ├── profile.ejs
│ └── edit.ejs
├── package.json
└── README.md

yaml
Copy code

---
## Screenshots

<img width="1906" height="980" alt="image" src="https://github.com/user-attachments/assets/9a461836-745e-408d-8491-7df77cf7f3bb" />
<img width="1902" height="988" alt="image" src="https://github.com/user-attachments/assets/75b96bac-c34a-44e9-bac0-7ccf9ca4562b" />
<img width="1892" height="973" alt="image" src="https://github.com/user-attachments/assets/e2c8a1ab-07ef-4087-ace5-3e8281106a67" />
<img width="1891" height="984" alt="Screenshot 2025-10-23 125046" src="https://github.com/user-attachments/assets/754c345e-afcc-4616-9a5f-0071391cfadb" />
<img width="1919" height="982" alt="image" src="https://github.com/user-attachments/assets/dd34631d-31ca-4faf-84c0-4e6a286c87b1" />


## ⚙️ Installation & Setup

### 1️⃣ Clone the repository

git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
2️⃣ Install dependencies
bash
Copy code
npm install
3️⃣ Setup environment variables
Create a .env file in the project root and add:

ini
Copy code
JWT_SECRET=shhhhh
MONGO_URI=mongodb://localhost:27017/authApp
PORT=3000
(Or replace with your actual MongoDB connection string)

4️⃣ Run the app
bash
Copy code
node app.js
Visit: 👉 http://localhost:3000

## 🔐 Authentication Flow
Register → /register
User details are hashed using bcrypt, stored in MongoDB, and a JWT is issued.

Login → /login
Passwords are compared securely using bcrypt.
On success, a JWT is signed and stored in browser cookies.

isLoggedIn Middleware
Verifies the JWT from cookies before allowing access to protected routes like /profile, /post, /edit/:id, etc.

Logout → /logout
Clears the cookie and redirects to the login page.

## 🧩 API Routes Overview
Route	Method	Description
/	GET	Renders homepage
/register	POST	Registers a new user
/login	POST	Logs in existing user
/profile	GET	Displays user profile & posts (Protected)
/post	POST	Creates a new post (Protected)
/like/:id	GET	Like/Unlike a post (Protected)
/edit/:id	GET	Renders edit page for a post
/update/:id	POST	Updates post content (Protected)
/logout	GET	Logs out the user

## 🧠 How It Works
When a user registers or logs in, a JWT is created:

js
Copy code
jwt.sign({ email: user.email, userid: user._id }, "shhhhh");
The token is stored as a browser cookie.

Each protected route uses:

js
Copy code
jwt.verify(req.cookies.token, "shhhhh");
to validate access.

Passwords are hashed using bcrypt before being stored in MongoDB.

🧑‍💻 Example User Flow
Go to /register → Create an account

Login at /login

Access /profile → Create a post

Like/unlike other posts

Edit your posts

Logout when done

## 🛠️ Dependencies
json
Copy code
"dependencies": {
  "bcrypt": "^5.1.0",
  "cookie-parser": "^1.4.6",
  "ejs": "^3.1.9",
  "express": "^4.18.2",
  "jsonwebtoken": "^9.0.2",
  "mongoose": "^7.0.3"
}
## 📜 License
This project is licensed under the MIT License.

## 💡 Author
Shibam Banik
## 👨‍🎓 B.Tech CSE (Blockchain Technology) @ VIT
💬 GitHub: https://github.com/Shibam802
