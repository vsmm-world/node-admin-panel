# Admin Control Panel Using Node.js

A learning project implementing a simple admin control panel with cookie/JWT-based authentication in Express.

## Features

- Admin registration and login
- JWT-based authentication delivered via cookies
- Auth middleware guarding the admin dashboard (`adminAuth`) and redirecting already-logged-in admins away from login/register (`chekAuth`)
- Logout flow that clears the auth cookie
- Server-rendered views with EJS (home, admin dashboard, login, register)

## Tech Stack

- Node.js, Express
- `jsonwebtoken` for token creation/verification
- `cookie-parser` for reading the JWT from cookies
- MongoDB via Mongoose / MongoDB driver
- `bcryptjs` for password hashing
- EJS for templating
- `nodemon` for development

## Project Structure

```
app.js              # Express app entry point & routes
auth/
├── auth.js         # adminAuth / chekAuth / logout middleware
└── route.js        # Admin auth routes (login/register/logout)
data/
├── data.js         # Data access helpers
└── route.js        # Data-related routes
db/
└── db.js           # MongoDB connection
models/
├── admin.js        # Admin schema
└── home.js         # Home/page data schema
views/
├── home.ejs
├── admin.ejs
├── adminLogin.ejs
└── adminRegister.ejs
public/
└── css/
```

## Getting Started

### Prerequisites
- Node.js 18+
- A running MongoDB instance

### Setup

```bash
git clone https://github.com/vsmm-world/Admin-Control-Panel-Using-Nodejs.git
cd Admin-Control-Panel-Using-Nodejs
npm install
```

Update the MongoDB connection details in `db/db.js`, then start the server:

```bash
npm start   # runs via nodemon
```

The app listens on the port defined by `PORT` (defaults to `3000`):

- `/` — home page
- `/admin` — protected admin dashboard
- `/admin/register` — admin registration
- `/admin/login` — admin login
- `/admin/logout` — clears the session cookie

## What This Demonstrates

- Building simple route-guard middleware (`adminAuth`, `chekAuth`) around a JWT cookie
- Separating auth routes/data routes/db config into small, focused modules

## Author

**Ravindra Valand**
- GitHub: [@vsmm-world](https://github.com/vsmm-world)
- Instagram: [@ravindra_valand](https://www.instagram.com/ravindra_valand/)

## License

Personal learning project, not intended for production use.
