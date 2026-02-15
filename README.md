# ProShop v2 (MERN eCommerce)

A full-stack eCommerce application built with **MongoDB, Express, React, Node.js**, and **Redux Toolkit**.

## Important Notes (Read First)
- This app requires a running **MongoDB database** and valid `.env` configuration before starting.
- The backend reads environment variables from a root `.env` file.
- Default payment method is **Cash on Delivery** (no external payment setup required).
- PayPal is optional and only needed if you choose PayPal checkout.
- Uploads are stored in `/uploads` (development) and served from `/var/data/uploads` in production mode.

## Prerequisites
- Node.js 18+ (recommended)
- npm 9+
- MongoDB Atlas (or local MongoDB)
- PayPal Developer client ID (optional, only for PayPal checkout)

## 1) Environment Setup
Create a `.env` file in the project root:

```env
NODE_ENV=development
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=replace_with_a_strong_secret
PAYPAL_CLIENT_ID=your_paypal_client_id # optional for PayPal flow
PAGINATION_LIMIT=8
```

## 2) Install Dependencies
From the project root:

```bash
npm install
cd frontend
npm install
cd ..
```

## 3) Run the App Successfully
Run backend + frontend together:

```bash
npm run dev
```

- Frontend: `http://localhost:3000`
- Backend API: `http://localhost:5000`

Run backend only:

```bash
npm run server
```

## 4) Seed the Database (Optional but Recommended)
Import sample products/users:

```bash
npm run data:import
```

Destroy seeded data:

```bash
npm run data:destroy
```

## 5) Build for Production

```bash
npm run build
npm start
```

## API Health Check
After backend starts, verify API is running:

- `GET http://localhost:5000/` (development mode)

## Common Setup Issues
- **`MONGO_URI` undefined / connection error:** Ensure `.env` exists in root and `MONGO_URI` is valid.
- **PayPal button not loading:** Verify `PAYPAL_CLIENT_ID` in `.env` (only needed if using PayPal).
- **Want easiest setup:** Keep payment method as Cash on Delivery at checkout.
- **Image upload fails:** Use `multipart/form-data` with field name `image`.
- **Port conflict:** Change `PORT` in `.env`.

## Tech Stack
- Backend: Express, Mongoose, JWT, Multer
- Frontend: React, Redux Toolkit, React Bootstrap, RTK Query

## License
MIT
