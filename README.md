# Serve2U

**Serve2U** is a cloud-based web application designed for football fans to order concession items directly to their seats. Users can pay securely via Stripe and avoid the halftime and pre-game rush at stadiums.

This project was developed as part of my Individual Project module (45 credits).

> **Note:** This was my first fullstack app with cloud integration, built before gaining proficiency in Node.js and React.js.

---

## Project Setup Guide

### Prerequisites
- Node.js  
- PHP  
- MySQL  
- Composer  

---

### Folder Structure

- `src/` — Source code including servers  
- `public/` — Served by Express; contains `index.html`, JS, and assets  
  - `HTML/` — HTML files  
  - `CSS/` — CSS files  
  - `backend/` — PHP files (includes database connection config)  
- `services/` — AWS Cognito service files for auth  
- `middleware/` — Authentication middleware  
- `controllers/` — Backend controllers  

---

## Installation

1. Clone the repo and navigate to the project folder:

   ```bash
   git clone https://github.com/riad-mammadov/Serve2U-Cloud-Based-Application
   npm install
   composer install
   
## Database Setup

CREATE DATABASE Serve2U;
USE Serve2U;
Import serve2udatabase.sql from the project root.

Update database config:

In src/controllers/auth.controller.ts:
const pool = createPool({
    host: 'localhost',
    user: 'your_sql_user',
    password: 'your_sql_password',
    database: 'Serve2U',
    port: 3306
});

In public/backend/dbconnection.php:
$localhost = "localhost:3306";
$db = "Serve2U";
$user = "your_sql_user";
$pwd = "your_sql_password";

## Start both Node and PHP servers concurrently:

npm run dev
Express server runs on http://localhost:3000
PHP server runs on http://localhost:8080
Ensure MySQL is running on port 3306.

## Usage:

Open http://localhost:3000 in your browser.
Sign up with a valid email (verification code sent via AWS SES).

## Staff Login:

Use the preconfigured staff account to access the Staff Dashboard:
Username: Test0033
Password: Password123@

## Stripe Demo Payments:

Card Number: 4242 4242 4242 4242
Expiry: Any future date
CVV: Any 3 digits
After placing orders, staff can manage them via the dashboard.

## To add menu items (staff):

Upload valid file types as per PHP validation.
Enter prices in pence (e.g., £14.50 = 1450).
Refresh the user’s cart page to see new items.

**Note**-
Early project with learning-focused implementation.
