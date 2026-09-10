# Fuel Tracker

![Angular](https://img.shields.io/badge/Angular-DD0031?logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-5FA04E?logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?logo=mongodb&logoColor=white)

Fuel Tracker is a university full-stack CRUD project for tracking fuel consumption. It has a complete basic flow in which users can register, log in, manage their cars, and save refueling records for each vehicle.

## About

I built the app mainly to practice the basics of the MEAN stack in a real use case. It is not meant to cover every feature a production fuel tracking system could have, but it does bring the most important CRUD parts together in one working application.

The frontend is made with Angular and Angular Material. The backend is an Express API that stores data in MongoDB through Mongoose.

After logging in, users can only see and manage their own cars and refueling entries. Passwords are hashed with bcrypt, and protected API routes use JWT authentication. The Angular side also protects the account pages, so they cannot be opened without logging in.

Each refueling entry stores the date, odometer reading, fuel amount, and unit price. The backend calculates the total cost. If the car already has an earlier entry, it also calculates fuel consumption from the odometer difference.

## Stack

| Area | Technologies |
|---|---|
| Frontend | Angular 19, Angular Material, TypeScript, RxJS |
| Backend | Node.js, Express, MongoDB, Mongoose |
| Authentication | JWT, bcrypt |
| Validation and testing | express-validator, Cypress |

## API

The backend runs at `http://localhost:5000` by default. Authentication is handled under `/api/auth`, car data under `/api/cars`, and refueling records under `/api/refuel`. A small `/ping` route is also available for checking whether the server is running.

## Setup

You need Node.js and a running MongoDB instance.

Create a `.env` file in the `backend` folder:

```env
PORT=5000
MONGO_URL=mongodb://localhost:27017/fuel-tracker
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

Cypress tests cover the main flows, including registration and login, adding a car with a refueling entry, and deleting a car. The backend, the frontend, and MongoDB must be running before you start the tests.

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

### Refueling Log
![Refueling log page](assets/images/refuel.png)

## What I Learned

This project helped me understand how the frontend and backend parts of a CRUD application work together. I also practiced protected routes, JWT authentication, Mongoose models, form validation, and end-to-end testing with Cypress.
