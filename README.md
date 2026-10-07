# Farm-Direct
🌱 Farm Direct — A full-stack farmer-to-customer marketplace platform for product management, online ordering, offers, payments, and real-time order tracking.
# 🌱 Farm Direct

**Farm Direct** is a full-stack farmer-to-customer marketplace platform designed to connect farmers directly with customers. Farmers can list and manage agricultural products, while customers can browse products, apply offers, add items to their cart, place orders, and track deliveries.

The platform also includes role-based access for **Customers, Farmers, and Administrators**, along with order management, offers, wallet management, and simulated payment functionality.

## 🚀 Features

### 👨‍🌾 Farmer
- Add, edit, and delete products
- Manage product prices and stock
- Create and manage offers
- View customer orders
- Track order status
- View earnings and wallet balance
- Request withdrawals

### 🛒 Customer
- Browse agricultural products
- Search and filter products
- View product details
- Add products to cart
- Apply available offers
- Apply eligible bank offers
- Calculate checkout total
- Place orders
- Select payment methods
- Track order status
- View order history

### 👨‍💼 Admin
- Dashboard with platform overview
- Manage users
- Manage products
- Manage offers
- Manage orders
- Manage payments
- Manage withdrawal requests
- Monitor farmers and customers

## 🔐 Authentication & Security

- JWT-based authentication
- Role-based authorization
- Password hashing using `bcrypt`
- Protected backend routes
- Server-side validation for important business logic
- Stock validation during order placement
- Backend-side price and discount calculation

## 💰 Order & Pricing System

The platform calculates the final order amount on the backend.

The calculation includes:

```text
Product Price × Quantity
        ↓
Product Discount
        ↓
Bank Discount
        ↓
Delivery Charge
        ↓
Final Order Amount
```

The backend recalculates the order amount instead of trusting values received from the frontend, helping prevent price manipulation.

## 📦 Order Tracking

Orders follow a delivery lifecycle:

```text
Placed
  ↓
Confirmed
  ↓
Packed
  ↓
Shipped
  ↓
Out for Delivery
  ↓
Delivered
```

Customers can track their orders, while farmers and administrators can update order statuses based on their roles.

## 🛠️ Tech Stack

### Frontend
- React.js
- Vite
- JavaScript
- CSS
- Framer Motion

### Backend
- Node.js
- Express.js
- REST APIs
- JWT
- bcrypt

### Storage
- JSON-based file storage for the current prototype

### Testing
- Node.js Test Runner
- Supertest

### Deployment
- Render

## 🏗️ Project Architecture

```text
                    FARM DIRECT
                         │
              ┌──────────┴──────────┐
              │                     │
         React Frontend        Node.js Backend
              │                     │
              │                  Express.js
              │                     │
              └────── REST API ─────┘
                                    │
                              JWT Authentication
                                    │
                              Business Logic
                                    │
                              JSON Data Storage
```

## 📁 Project Structure

```text
farm-direct/
│
├── frontend/
│   ├── src/
│   │   ├── App.jsx
│   │   ├── Customer.jsx
│   │   ├── Panel.jsx
│   │   ├── Shared.jsx
│   │   ├── Manual.jsx
│   │   ├── ui.jsx
│   │   ├── api.js
│   │   ├── main.jsx
│   │   └── styles.css
│   ├── package.json
│   └── vite.config.js
│
├── backend/
│   ├── src/
│   │   ├── app.js
│   │   ├── server.js
│   │   └── db.js
│   ├── tests/
│   │   └── api.test.js
│   └── package.json
│
├── render.yaml
├── README.md
└── package.json
```

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone <YOUR-GITHUB-REPOSITORY-URL>
cd farm-direct
```

### 2. Install dependencies

```bash
npm install
```

Install frontend dependencies:

```bash
cd frontend
npm install
```

Install backend dependencies:

```bash
cd ../backend
npm install
```

### 3. Start the backend

```bash
cd backend
npm start
```

### 4. Start the frontend

Open another terminal:

```bash
cd frontend
npm run dev
```

The application will then be available through the Vite development server.

## 🧪 Testing

Backend API tests can be executed using:

```bash
cd backend
npm test
```

The tests cover areas such as:

- User authentication
- Invalid login handling
- Product search
- Order quotation
- Role-based authorization
- Order lifecycle
- Wallet operations

## 💳 Payment

The current project uses **simulated payment processing** for demonstration purposes.

For a production application, a real payment gateway such as Razorpay, Cashfree, Stripe, or another suitable provider can be integrated.

## 🗄️ Database

The current prototype uses JSON-file-based storage for simplicity and demonstration.

For production deployment, the system can be migrated to:

- PostgreSQL
- MongoDB
- MySQL

A production database would provide better scalability, concurrency control, transactions, indexing, and data integrity.

## 🔮 Future Enhancements

- Real payment gateway integration
- PostgreSQL/MongoDB database
- Cloud image storage
- Email/SMS notifications
- Real-time order tracking
- Advanced farmer analytics
- Customer reviews and ratings
- Delivery partner integration
- Inventory management
- Production-grade transaction handling
- Stronger validation and security
- Mobile application

## 🎯 Project Objective

The main objective of Farm Direct is to create a digital marketplace that reduces the dependency on intermediaries and provides a convenient platform for farmers to sell agricultural products directly to customers.

## 👥 Team

| Role | Team Member |
|---|---|
| Frontend Developer | B. Prakash Abhinay |
| Backend Developer | P. Sandeep Sagar |
| Testing | Bachu Rithwik |
| Payments, Offers & Order Tracking | Team Member |

## 📌 Project Status

**Status:** Completed Prototype / Academic Project

Farm Direct demonstrates a complete full-stack marketplace workflow including authentication, product management, cart and checkout, offers, order management, role-based access control, wallet management, and API testing.
