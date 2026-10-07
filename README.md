<h1 align="center">CanteenQ</h1>
<p align="center"><b>Smart Canteen Pre-Order and Queue Management System</b></p>
<p align="center">
  <img src="https://img.shields.io/badge/Stack-MERN-success" />
  <img src="https://img.shields.io/badge/Frontend-React-61DAFB" />
  <img src="https://img.shields.io/badge/Backend-Node.js%20%2B%20Express-339933" />
  <img src="https://img.shields.io/badge/Database-MongoDB-47A248" />
  <img src="https://img.shields.io/badge/Auth-JWT-blue" />
</p>

CanteenQ lets students pre-order food for a selected break and collect it with a **token number** and **pickup code**, without standing in a queue. The canteen admin manages breaks and the menu, moves each order through **Start cooking → Mark ready → Hand over**, and uses a **preparation sheet** to cook only what has been ordered, which reduces food waste.

This repository is the **MERN** version (React frontend). The same project is also built with Angular in the **MEAN** repository.

---

## Features

**Student**
- Register and log in securely (JWT authentication)
- Browse the menu and add items to a cart
- Order for a selected break
- View a digital ticket with token number and pickup code
- Track order status: Placed, Cooking, Ready, Handed over

**Admin**
- Create and manage breaks (time slots)
- Menu manager: add, edit and remove items
- Order board: Start cooking, Mark ready, Hand over
- Preparation sheet showing the quantity of each item to cook
- Reports page with order statistics

## Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | React, JavaScript, CSS |
| Backend | Node.js, Express.js |
| Database | MongoDB with Mongoose |
| Security | JWT, password hashing, role-based access |
| Tools | VS Code, Postman, Git |

## Architecture

```
React client  →  Express REST API (Node.js)  →  MongoDB
```

## Project Structure

```
canteenq-mern/
├── server/     # Express API, Mongoose models, routes, JWT auth
└── client/     # React frontend
```

## Screenshots

| Login | Menu |
|-------|------|
| ![Login](screenshots/login.png) | ![Menu](screenshots/menu.png) |

| Cart | Ticket |
|------|--------|
| ![Cart](screenshots/cart.png) | ![Ticket](screenshots/ticket.png) |

| Admin Board | Preparation Sheet |
|-------------|-------------------|
| ![Admin](screenshots/admin-board.png) | ![Prep](screenshots/prep-sheet.png) |

| Menu Manager | Reports |
|--------------|---------|
| ![Menu Manager](screenshots/menu-manager.png) | ![Reports](screenshots/reports.png) |

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (LTS version)
- A MongoDB database (local, or free [MongoDB Atlas](https://www.mongodb.com/atlas))

### 1. Clone the repository
```bash
git clone https://github.com/YOUR-USERNAME/canteenq-mern.git
cd canteenq-mern
```

### 2. Set up the server
```bash
cd server
npm install
```
Create a `.env` file (see `.env.example`):
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
```
Load the sample data (first time only) and start the server:
```bash
npm run seed
npm run dev
```

### 3. Set up the client
Open a second terminal:
```bash
cd client
npm install
npm run dev
```
Open the address shown in the terminal in your browser.

### Demo accounts
| Role | Email | Password |
|------|-------|----------|
| Admin | YOUR-ADMIN-EMAIL | YOUR-ADMIN-PASSWORD |
| Student | YOUR-STUDENT-EMAIL | YOUR-STUDENT-PASSWORD |

## How It Works
1. The admin creates a break (for example, a lunch break).
2. The student logs in, picks the break, adds items to the cart and places the order.
3. The student receives a ticket with a token number and pickup code.
4. The admin reads the preparation sheet, cooks the required quantity, and moves the order through Start cooking, Mark ready and Hand over.
5. The student shows the pickup code and collects the food.

## Future Enhancements
- Online payment
- SMS or push notification when an order is ready
- Mobile application
- Demand prediction from past reports

## Author
**YOUR NAME**
[LinkedIn](YOUR-LINKEDIN-URL) | [GitHub](https://github.com/YOUR-USERNAME) | your.email@example.com

## License
This project is licensed under the MIT License.
