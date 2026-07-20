# CodeAlpha_ECommerceStore

A simple full-stack e-commerce store built for the CodeAlpha Full Stack Development Internship — Task 1.

## Features
- Product listing with category filter
- Product details page
- Shopping cart (session-based: add, update quantity, remove)
- Order processing / checkout with shipping info
- User registration and login (passwords hashed with bcrypt)
- Order history per user
- SQLite database (products, users, orders, order_items)

## Tech Stack
- **Frontend:** HTML, CSS, vanilla JavaScript
- **Backend:** Node.js + Express.js
- **Database:** SQLite (via `better-sqlite3`)

## Project Structure
```
CodeAlpha_ECommerceStore/
├── server.js           # App entry point
├── db.js               # Database connection + schema
├── seed.js             # Sample product data (auto-runs on first start)
├── routes/
│   ├── products.js      # GET /api/products, /api/products/:id
│   ├── auth.js          # register / login / logout / me
│   ├── cart.js          # session-based cart CRUD
│   └── orders.js        # checkout + order history
└── public/              # Frontend (served statically)
    ├── index.html        # Product listing
    ├── product.html       # Product details
    ├── cart.html          # Shopping cart
    ├── login.html / register.html
    ├── checkout.html
    ├── orders.html         # Order history
    ├── css/style.css
    └── js/                 # main.js, product.js, cart.js, auth.js, checkout.js, orders.js, common.js
```

## Setup & Run

```bash
# 1. Install dependencies
npm install

# 2. Start the server (sample products auto-seed on first run)
npm start

# 3. Open in your browser
http://localhost:3000
```

## How to Use
1. Browse products on the homepage, filter by category.
2. Add items to your cart from the listing or product detail page.
3. View/edit your cart at `/cart.html`.
4. Register or log in — an account is required to place an order.
5. Go to checkout, enter shipping details, and place the order.
6. View your order history at `/orders.html`.

## Notes
- The cart is stored in the server session (cookie-based), so it persists per browser session without needing to be logged in — but placing an order requires login.
- The database file `store.db` is created automatically the first time you run the app.
- To reset the database, simply delete `store.db` and restart the server.
