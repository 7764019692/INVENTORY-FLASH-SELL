# 🔥 Flash Sale Inventory Management System

A mini **e-commerce flash sale platform** built with **FastAPI**, **SQLite**, and a **modern frontend (HTML, CSS, JavaScript)**.  
The system focuses on **correct inventory handling**, **no overselling**, and a **realistic UPI payment simulation**.

---

## 🚀 Overview

During flash sales, multiple users may attempt to buy the same product simultaneously.  
This project demonstrates how to:

- Prevent overselling
- Avoid false out-of-stock situations
- Update inventory **only after payment success**
- Provide a realistic checkout experience (UPI QR simulation)

---

## ✨ Features

### 🔐 Authentication
- Simple login using browser `sessionStorage`
- Unauthorized users are redirected to the login page

### 🛒 Flash Sale Products
- Product cards with price and live stock
- “Only X left” indicator
- Buy Now disabled automatically when stock reaches 0

### 💳 Payment Flow (UPI Simulation)
- Pay Now button
- UPI QR displayed after clicking Pay Now
- “I Have Paid” confirmation
- Cancel payment option

### 📦 Inventory Management
- Stock is **NOT** reduced on Buy Now
- Stock is reduced **ONLY** after payment confirmation
- Prevents revenue loss from abandoned checkouts

---

## 🧠 Key Principle

> **Reduce stock only after payment success, not before.**

This mirrors real-world systems like Flipkart and Amazon.

---

## 🧱 Tech Stack

### Backend
- **FastAPI** – REST APIs
- **SQLite** – Inventory database
- **Python** – Business logic
- **Repository Pattern** – Clean separation of concerns

### Frontend
- **HTML** – Structure
- **CSS** – Modern UI (cards, grid, buttons)
- **JavaScript** – API calls, events, dynamic rendering

### Assets
- **Static files** – CSS, JS, images
- **UPI QR image** – Payment simulation

### Scalability (Conceptual)
- **Redis** – Explained for high-concurrency reservations (atomic ops + TTL)

---

## 📁 Project Structure

inventory-system/
│
├── app/
│ ├── main.py # API routes
│ ├── database.py # SQLite DB setup
│ ├── repository.py # DB operations
│ └── seed_data.py # Initial product data
│
├── static/
│ ├── login.html # Login page
│ ├── index.html # Flash sale page
│ ├── payment.html # Payment page
│
│ ├── css/
│ │ └── style.css
│
│ ├── js/
│ │ ├── auth.js
│ │ ├── products.js
│ │ └── payment.js
│
│ └── assets/
│ └── upi_qr.jpeg # UPI QR image
│
└── inventory.db


---

## 🔁 User Flow

1. User logs in
2. Flash sale products are displayed
3. User clicks **Buy Now**
4. Redirected to payment page
5. Clicks **Pay Now**
6. UPI QR code is shown
7. User confirms payment
8. Backend updates stock
9. User returns to flash sale page with updated inventory

---

## 🔐 Payment Note

⚠️ This project uses a **simulated payment flow**.

> In production, payment confirmation would be handled via secure payment gateway webhooks.  
> Here, the “I Have Paid” button simulates success for demo and interview purposes.

---

## 🧠 Redis (Conceptual)

Redis is described as a **high-speed, in-memory reservation layer** to:
- Handle high concurrency
- Perform atomic reservations
- Use TTL for abandoned carts
- Prevent race conditions

(Ready to integrate for scaling.)

---

## ▶️ Run Locally

### 1️⃣ Install dependencies
```bash
pip install fastapi uvicorn
2️⃣ Start server
python -m uvicorn app.main:app --reload
3️⃣ Open in browser
http://127.0.0.1:8000/login.html
🧪 APIs
Get products
GET /products
Confirm payment
POST /confirm-payment/{sku}
r

