# PostgreSQL-Authenticated E-commerce Site

This project is a simple login authentication system using a PostgreSQL database. After successful login, the user is redirected to a basic e-commerce site interface. The project is built using Node.js, Express, and PostgreSQL.

## Features

- Secure login using PostgreSQL as the backend database
- Basic user session handling
- Simple e-commerce homepage after login

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: PostgreSQL
- **Frontend**: HTML, CSS (Basic template)
- **ORM/Query**: `pg` Node package for PostgreSQL integration

---

## Prerequisites

Before running the project, make sure you have the following installed:

- Node.js (v14 or later)
- PostgreSQL
- Git (optional)

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/postgres-ecommerce-login.git
cd postgres-ecommerce-login
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Setup PostgreSQL Database

#### a. Create a new PostgreSQL database:

```sql
CREATE DATABASE ecommerce_auth;
```

#### b. Create the `users` table:

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL
);
```

#### c. Insert a test user:

```sql
INSERT INTO users (username, password)
VALUES ('testuser', 'testpass');  -- In a real app, store hashed passwords
```

> **Note**: For production apps, always hash passwords (e.g., using bcrypt)

### 4. Configure Environment Variables

Create a `.env` file in the root directory with:

```env
PORT=3000
DB_USER=your_db_username
DB_PASSWORD=your_db_password
DB_HOST=localhost
DB_PORT=5432
DB_NAME=ecommerce_auth
```

### 5. Run the App

```bash
npm start
```

Visit `http://localhost:3000` in your browser.

---

## Project Structure

```
├── public/
│   └── styles.css         # Basic styling
├── views/
│   ├── login.html         # Login form
│   └── dashboard.html     # E-commerce homepage
├── .env                   # Environment variables
├── app.js                 # Main server file
├── db.js                  # PostgreSQL connection logic
└── package.json
```

---

## Usage

1. Navigate to the login page (`http://localhost:3000`)
2. Enter the test credentials:
   - **Username**: `testuser`
   - **Password**: `testpass`
3. On successful login, you'll be redirected to the e-commerce homepage.

---

## Future Improvements

- Password hashing using bcrypt
- User registration page
- E-commerce features: product listings, cart, checkout
- Better session handling and middleware

---

## License

This project is open-source and available under the MIT License.
