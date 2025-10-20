Product API - Express.js Assignment (Week 2)

A RESTful API built with Express.js and MongoDB that manages product data.
This project demonstrates backend fundamentals — CRUD operations, middleware, authentication, error handling, and advanced query features.

🚀 Features

CRUD operations for managing products

Custom middleware for logging, validation, and authentication

Global error handling

Filtering, pagination, and search functionality

MongoDB integration using Mongoose

Environment variable configuration using dotenv

🛠️ Technologies Used

Node.js

Express.js

MongoDB / Mongoose

dotenv

body-parser

uuid (for unique product IDs)

Postman (for API testing)

📂 Project Structure
week2_main/
│
├── server.js                # Main server file
├── config/
│   └── db.js                # MongoDB connection setup
│
├── routes/
│   └── products.js          # Product routes
│
│
├── middleware/
│   ├── logger.js            # Request logging
│   ├── auth.js              # Authentication middleware
│   ├── errorHandler.js      # Global error handling
│   └── validateProduct.js   # Validation middleware
│
├── models/
│   └── Product.js           # Product schema
│
├── .env                     # Environment variables
└── README.md                # Project documentation

⚙️ Setup Instructions
1️⃣ Clone the Repository
git clone https://github.com/YOUR_USERNAME/express-js-server-side-framework-Olamide101-3mt.git
cd express-js-server-side-framework-Olamide101-3mt

2️⃣ Install Dependencies
npm install

3️⃣ Create a .env File

Create a .env file in your root directory and add:

MONGO_URI=your_mongodb_connection_string
PORT=3000


(You can use a local MongoDB instance or a MongoDB Atlas URI.)

4️⃣ Start the Server
node server.js


You should see:

✅ MongoDB connected successfully
Server running on http://localhost:3000

🧠 API Documentation
Base URL
http://localhost:3000/api/products

🔐 Authentication

All protected routes require an API key header:

authorization: Bearer secret123


🧾 Endpoints
Method	Endpoint	Description
GET	/api/products	Get all products (supports filtering, pagination, and search)
GET	/api/products/:id	Get a specific product by ID
POST	/api/products	Create a new product
PUT	/api/products/:id	Update an existing product
DELETE	/api/products/:id	Delete a product
GET	/api/products/stats	Get product statistics (e.g., count by category)
🧪 Example Request (Create Product)

POST http://localhost:3000/api/products

Headers:

x-api-key: mysecretkey
Content-Type: application/json


Body:

{
  "name": "Wireless Mouse",
  "description": "Ergonomic mouse with USB receiver",
  "price": 25.99,
  "category": "electronics",
  "inStock": true
}


Response:

{
  "message": "Product created successfully",
  "product": {
    "_id": "6714df832f...",
    "name": "Wireless Mouse",
    "description": "Ergonomic mouse with USB receiver",
    "price": 25.99,
    "category": "electronics",
    "inStock": true
  }
}

⚡ Error Handling

Custom error handling middleware ensures clean and consistent API responses:

400 — Validation errors

401 — Unauthorized

404 — Resource not found

500 — Server errors

Example:

{
  "status": 404,
  "message": "Product not found"
}

🧩 Environment Example (.env.example)
MONGO_URI=your_mongodb_connection_string
PORT=3000
API_KEY=mysecretkey

📜 License

This project is part of the PLP MERN Stack Scholarship Program (Week 2 Assignment).
Developed by Olamide Wahab.

Would you like me to make this README use the Bearer token version of your authentication instead of x-api-key? I can adjust it to perfectly match your current setup.
