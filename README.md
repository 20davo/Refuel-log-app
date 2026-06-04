# Refuel Log App

Refuel Log App is a university full-stack CRUD project for tracking fuel consumption. It has a complete basic flow: users can register, log in, manage their cars, and save refuel records for each vehicle.

## About

I built the app mainly to practice the basics of the MEAN stack in a real use case. It is not meant to cover every feature a production fuel tracking system could have, but it does connect the most important CRUD parts into one working application.

The frontend is made with Angular and Angular Material. The backend is an Express API that stores data in MongoDB through Mongoose.

After logging in, users can only see and manage their own cars and refuel entries. Passwords are hashed with bcrypt, and private requests use JWT authentication. The Angular side also protects the account pages, so they cannot be opened without a valid login.

Each refuel entry stores the date, odometer reading, fuel amount, and unit price. The backend calculates the total cost. If the car already has an earlier entry, it also calculates fuel consumption from the odometer difference.

## Stack

| Area | Technologies |
|---|---|
| Frontend | Angular 19, Angular Material, TypeScript, RxJS |
| Backend | Node.js, Express, MongoDB, Mongoose |
| Authentication | JWT, bcrypt |
| Validation and testing | express-validator, Cypress |

## API

The backend runs on `http://localhost:5000` by default. Authentication is handled under `/api/auth`, car data under `/api/cars`, and refuel records under `/api/refuel`. A small `/ping` route is also available for checking whether the server is running.

## Setup

Create a `.env` file in the `backend` folder:

```env
PORT=5000
MONGO_URL=mongodb://localhost:27017/refuel-log
JWT_SECRET=your_secret_key
```

Start the backend:

```bash
cd backend
npm install
node server.js
```

Start the frontend:

```bash
cd frontend
npm install
npm start
```

The frontend runs at `http://localhost:4200`.

## Testing

Cypress tests cover the main flows, including login, car creation, adding a refuel entry, and deleting one.

```bash
cd frontend
npm run cypress:open
npm run cypress:run
```

## Screenshots

### Registration
![Registration page](assets/images/register.png)

### Login
![Login page](assets/images/login.png)

### My Cars
![Cars page](assets/images/cars.png)

### Refuel Log
![Refuel log page](assets/images/refuel.png)

## What I Learned

This project helped me understand how the frontend and backend parts of a CRUD application work together. I also practiced protected routes, JWT authentication, Mongoose models, form validation, and end-to-end testing with Cypress.
