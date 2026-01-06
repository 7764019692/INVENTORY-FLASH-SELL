# 🔥 Flash Sale Inventory Management System

A mini **e-commerce flash sale platform** built using **FastAPI**, **SQLite**, **Redis (conceptual)** and a **modern frontend (HTML, CSS, JavaScript)**.  
The system focuses on **correct inventory handling**, **no overselling**, and a **realistic UPI payment simulation**.

---

## 🚀 Project Overview

In flash sale scenarios, multiple users may try to purchase the same product at the same time.  
This project demonstrates how to:

- Prevent overselling
- Avoid false out-of-stock situations
- Update stock **only after successful payment**
- Provide a realistic checkout and payment flow

---

## ✨ Features

### 🔐 Authentication
- Simple login using browser sessionStorage
- Unauthorized users are redirected to login page

### 🛒 Flash Sale Products
- Product listing with price and remaining stock
- “Only X left” indicator
- Buy Now disabled automatically when stock is 0

### 💳 Payment Flow (UPI Simulation)
- Pay Now button
- UPI QR code shown after clicking Pay Now
- “I Have Paid” confirmation
- Cancel payment option

### 📦 Inventory Management
- Stock is **NOT reduced on Buy Now**
- Stock is reduced **ONLY after payment confirmation**
- Prevents revenue loss from abandoned checkouts

---

## 🧠 Key Design Principle

> **Stock should be reduced only after payment success, not before.**
