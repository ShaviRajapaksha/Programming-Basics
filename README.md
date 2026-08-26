# MERN Stack JWT Authentication & Authorization

A full-stack authentication and authorization system built using the MERN stack (MongoDB, Express.js, React, Node.js) with JSON Web Tokens (JWT) and HttpOnly cookies.

## Features

- **User Authentication**: Sign Up, Log In, and Log Out with password hashing (bcrypt).
- **Secure JWT Handling**: Tokens are stored safely in `HttpOnly` cookies to mitigate XSS attacks.
- **Role-Based Authorization (RBAC)**: Protected routes for `User` and `Admin` roles.
- **Persistent Sessions**: React state synchronizes with authentication status on page refreshes.
- **RESTful API**: Clean backend routes with custom middleware for token verification.

---

## Tech Stack

- **Frontend**: React, React Router, Axios / Fetch API, Context API (or Redux)
- **Backend**: Node.js, Express.js
- **Database**: MongoDB with Mongoose ODM
- **Security**: JSON Web Tokens (`jsonwebtoken`), `bcryptjs`, `cookie-parser`, `cors`

---
