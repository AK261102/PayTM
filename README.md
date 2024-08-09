Paytm-Like Application:

PROJECT DOCUMENTATION: https://drive.google.com/file/d/1-8mwTsC_otelMqQPcd-Klr_tC06xBxzJ/view

1. Overview
   This project aims to build a Paytm-like application, implementing features such as user and merchant login, money transfer via phone number or QR code, and more. The application uses modern web technologies, including Next.js for the frontend, Express for the backend, Postgres as the database, and Prisma as the ORM.

2. Table of Contents
   1.Features

2.Tech Stack

3.Installation

4.Project Structure

5.Usage

6.Database Schema

7.API Routes

8.Frontend Components

9.Contributing

3. Features
   3.1 User Features

---

1.User Login: Supports authentication via email or phone.

2.Money Transfer: Transfer money via phone number, name, or QR code.

3.Withdraw Balance: Withdraw balance back to the bank.

## 3.2 Merchant Features(FUTURE SCOPES FOR IMPROVEMENT)

1.Merchant Login: Login via Google.

2.QR Code Generation: Generate QR codes for payment acceptance.

3.Payment Notifications: Merchants receive alerts upon successful payment.

4.Automatic Withdrawal: Merchants’ balance is automatically transferred to the bank every two days.

4. Tech Stack
   Frontend: Next.js, Tailwind CSS

Backend: Express.js, Node.js

Database: PostgreSQL

ORM: Prisma

Auxiliary Tools: Turborepo for project management, Recoil for state management, NextAuth for authentication

5. Installation

Clone the repository: https://github.com/AK261102/PayTM.git

bash

Copy code
git clone :

Navigate to the project directory:

bash

Copy code
cd paytm-like-app
Install dependencies:

bash

Copy code
npm install
Set up the database:

Create a new database in PostgreSQL.

Update the .env file with your database URL.

Run Prisma migrations:

bash

Copy code

npx prisma migrate dev

Run the development server:

bash
Copy code
npm run dev 6. Project Structure

apps/user-app: Contains the frontend application for users.

apps/merchant-app: Contains the frontend application for merchants.

packages/db: Handles the database client and schema using Prisma.

packages/store: Manages global state using Recoil.

packages/auth: Contains authentication logic using NextAuth.

7. Usage

7.1 Running the User App

To run the user application, use:

bash
Copy code

npm run dev --workspace=apps/user-app

7.2 Running the Merchant App
To run the merchant application, use:

bash
Copy code

npm run dev --workspace=apps/merchant-app

8. Database Schema
   The database schema includes tables for User, Merchant, and transactions. The schema is managed using Prisma ORM.

8.1 User Table

id: Integer, Primary Key, Auto-increment

name: String, Nullable

email: String, Unique, Nullable

phone: String, Unique

password: String

8.2 Merchant Table

id: Integer, Primary Key, Auto-increment

name: String, Nullable

email: String, Unique

auth_type: Enum (Google, GitHub)

9. API Routes

9.1 User Routes

POST /api/auth/login: Authenticate user.

GET /api/user/balance: Get user balance.

9.2 Merchant Routes

POST /api/auth/merchant/login: Authenticate merchant.

GET /api/merchant/transactions: Get merchant transactions.

10. Frontend Components

The frontend is structured using components for reusability and modularity. Some key components include:

AuthProvider: Manages authentication state.

AppBar: The main navigation bar for the application.

TransactionList: Displays a list of transactions.

11. Contributing

Contributions are welcome! Please follow the steps below to contribute:

Fork the repository.

Create a new branch (git checkout -b feature-branch).

Commit your changes (git commit -m 'Add new feature').

Push to the branch (git push origin feature-branch).

Open a pull request.
