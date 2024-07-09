# 💻 Question and answer Rest API

## 🚀 Getting started

To get the Node server running locally:

- Clone this repo
- `npm install` to install all required dependencies
- Create MongoDb Cluster and Get Connection MongoDb URI
- Set environment variables in `config.env` under `./config/env`

  - Set `PORT = <YOUR_PORT>`
  - Set `MONGO_URI = <YOUR_MONGO_URI>`
  - Set `JWT_SECRET_KEY = <YOUR_SECRET_KEY>`
  - Set `JWT_EXPIRE = <YOUR_JWT_EXPIRE_TIME>`
  - Set `SMTP_HOST=<YOUR_SMTP_HOST>`
  - Set `SMTP_PORT=<SMTP_PORT>`
  - Set `SMTP_EMAIL=<YOUR_GMAIL_EMAIL>`
  - Set `SMTP_PASS=<YOUR_GMAIL_PASSWORD>`

- `npm start` to start the local server

## 👨🏻‍💻 Application Structure

- `app.js` - The entry point to our application. This file defines our express server and connects it to MongoDB using mongoose. It also inncludes the routes we'll be using in the application.
- `config/` - This folder contains configuration for central location environment variables and other configurations.
- `routes/` - This folder contains the route definitions (answer, question etc. ) for our API.
- `models/` - This folder contains the schema definitions for our Mongoose models (User, Question).
- `controllers/` - This folder contains controllers for our API.
- `public/` - This folder contains static files for our API.
- `middlewares/` - This folder contains middlewares for our API.
- `helpers/` - This folder contains helper functions for adapting 3rd party libraries for our API.

## ‼️ Error Handling

In `middlewares/errors/errorHandler.js`, we define a error-handling middleware for handling Mongoose's errors and our own errors.

## 🔐 Authentication

Requests are authenticated using the `Authorization` header and value `Bearer: {{token}}`. with a valid JWT.

We define express middlewares in `middlewares/authorization/auth.js` that can be used to authenticate requests. The `required` middlewares returns `401` or `403`.
