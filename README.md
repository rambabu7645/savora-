# Savora — Restaurant Ordering & Management System (MERN)

A full-stack MCA mini project built with React + Vite, Node.js, Express, and MongoDB.
Includes secure cookie-based JWT authentication, customer/admin roles, menu CRUD, cart, order placement, order history, and admin order management.

## Requirements
- Node.js 18+
- MongoDB Community Server running locally, or a MongoDB Atlas connection string
- npm

## 1. Configure the backend
```bash
cd server
cp .env.example .env
npm install
npm run seed
npm run dev
```
On Windows PowerShell, copy the environment template with:
```powershell
Copy-Item .env.example .env
```
The seed command creates sample menu items and an admin account if they do not already exist:
- Email: `admin@savora.local`
- Password: `Admin@12345`
Change the seeded password immediately for any real deployment. Seed is for local development only.

## 2. Start the frontend (new terminal)
```bash
cd client
npm install
npm run dev
```
Open the Vite URL printed in the terminal (usually http://localhost:5173).

## Environment variables
See `server/.env.example`. Set a long random `JWT_SECRET`. For MongoDB Atlas, replace `MONGODB_URI`.
For production, use HTTPS and set `COOKIE_SECURE=true`; configure `CLIENT_URL` to your frontend origin.

## Features
- Register, login, logout, current-user session restore
- Password hashing with bcrypt
- JWT stored in an HttpOnly cookie (not localStorage)
- Role-based admin routes
- Browse/search/filter menu
- Cart and checkout with server-side price validation
- Customer order history
- Admin menu create/read/update/delete
- Admin order listing and status updates
- Express request validation, centralized errors, Helmet, rate limiting, CORS credentials
- Responsive UI and demo seed data

## Important project notes
- The frontend sends credentials with `fetch(..., { credentials: "include" })`.
- Prices and order totals are calculated by the server from database menu records.
- This is an educational project. Before public deployment, add email verification, password reset, stronger audit logging, payment-provider integration, automated tests, and production monitoring.
