# Silque E-commerce Platform

## Project Overview

Silque is a modern, full-stack e-commerce web application designed for scalability, performance, and a seamless user experience. It features a robust backend built with Node.js, Express, and MongoDB, and a fast, interactive frontend using React, Vite, and TailwindCSS. The platform supports user authentication, product management, shopping cart, order processing, payment integration, and real-time analytics. It leverages cloud services for image hosting (Cloudinary), caching (Upstash Redis), and payment processing (Stripe), making it production-ready for real-world deployments.

---

## In-Depth Project Structure

```
E-commerce/
│
├── backend/                        # Node.js/Express backend API
│   ├── controllers/                # Route controllers (business logic)
│   │   ├── analytics.controller.js # Analytics endpoints
│   │   ├── auth.controller.js      # Auth (login, signup, logout, tokens)
│   │   ├── cart.controller.js      # Cart operations
│   │   ├── coupon.controller.js    # Coupon management
│   │   ├── payment.controller.js   # Stripe payment integration
│   │   └── product.controller.js   # Product CRUD
│   ├── lib/                        # Utility libraries/services
│   │   ├── cloudinary.js           # Cloudinary image upload config
│   │   ├── db.js                   # MongoDB connection
│   │   ├── redis.js                # Upstash Redis client
│   │   └── stripe.js               # Stripe client setup
│   ├── middleware/                 # Express middleware (auth, error handling)
│   │   └── auth.middleware.js      # JWT authentication middleware
│   ├── models/                     # Mongoose models (data schemas)
│   │   ├── coupon.model.js         # Coupon schema
│   │   ├── order.model.js          # Order schema
│   │   ├── product.model.js        # Product schema
│   │   └── user.model.js           # User schema (with password hashing)
│   ├── routes/                     # Express route definitions
│   │   ├── analytics.route.js      # /api/analytics
│   │   ├── auth.route.js           # /api/auth
│   │   ├── cart.route.js           # /api/cart
│   │   ├── coupon.route.js         # /api/coupons
│   │   ├── payment.route.js        # /api/payments
│   │   └── product.route.js        # /api/products
│   └── server.js                   # Main backend entry point (Express app)
│
├── frontend/                       # React frontend (Vite, TailwindCSS)
│   ├── public/                     # Static assets (logo, images)
│   ├── src/
│   │   ├── components/             # Reusable UI components
│   │   │   ├── Navbar.jsx          # Navigation bar
│   │   │   ├── ProductCard.jsx     # Product display card
│   │   │   ├── CartItem.jsx        # Cart item component
│   │   │   ├── LoadingSpinner.jsx  # Loading indicator
│   │   │   └── ...                 # Other UI components
│   │   ├── lib/                    # Frontend utilities
│   │   │   ├── axios.js            # Axios instance/config
│   │   │   └── theme.js            # Theme toggling logic
│   │   ├── pages/                  # Page-level components (route targets)
│   │   │   ├── HomePage.jsx        # Home page
│   │   │   ├── LoginPage.jsx       # Login form
│   │   │   ├── SignUpPage.jsx      # Signup form
│   │   │   ├── AdminPage.jsx       # Admin dashboard
│   │   │   ├── CartPage.jsx        # Shopping cart
│   │   │   ├── CategoryPage.jsx    # Product category view
│   │   │   ├── ProductPage.jsx     # Product details
│   │   │   ├── PurchaseSuccessPage.jsx # Payment success
│   │   │   └── PurchaseCancelPage.jsx  # Payment cancel
│   │   ├── stores/                 # Zustand state stores
│   │   │   ├── useUserStore.js     # User/auth state
│   │   │   ├── useCartStore.js     # Cart state
│   │   │   ├── useProductStore.js  # Product state
│   │   │   └── useShopStore.js     # Shop/global state
│   │   ├── App.jsx                 # Main React app (routing, layout)
│   │   ├── main.jsx                # React entry point
│   │   └── index.css               # Global styles (TailwindCSS)
│   ├── package.json                # Frontend dependencies/scripts
│   ├── vite.config.js              # Vite config (proxy, plugins)
│   ├── tailwind.config.js          # TailwindCSS config
│   └── postcss.config.js           # PostCSS config
│
├── Products/                       # Example product images
│   ├── Jacket.jpg
│   ├── shoes.jpg
│   └── t-shirt.avif
│
├── .env                            # Environment variables (API keys, secrets)
├── package.json                    # Root dependencies/scripts (backend, build)
└── README.md                       # Project documentation
```

---

## Features

- **User Authentication:** Signup, login, JWT-based sessions, refresh tokens, secure cookies.
- **Admin Dashboard:** Product management, analytics, coupon creation.
- **Product Catalog:** Category browsing, product details, search, recommendations.
- **Shopping Cart:** Add/remove items, quantity management, persistent cart.
- **Checkout & Payments:** Stripe integration for secure payments, order confirmation, cancel flow.
- **Order Management:** Order history, admin order view.
- **Cloudinary Integration:** Fast, reliable image uploads and CDN delivery.
- **Upstash Redis:** Caching for performance, rate limiting, session storage.
- **Analytics:** Real-time sales and user analytics for admins.
- **Responsive UI:** Mobile-first, modern design with TailwindCSS and Framer Motion.
- **State Management:** Zustand for global state (user, cart, products).
- **API Security:** CORS, environment-based secrets, secure cookies, input validation.

---

## Development & Deployment Notes

- **Case Sensitivity:** All import paths and filenames must match exactly (Linux is case-sensitive).
- **Environment Variables:** Store all secrets and API keys in `.env` (never commit secrets).
- **Build Scripts:** The root `package.json` manages both backend and frontend build/install.
- **Deployment:** Ready for Vercel, Render, or any Node.js-compatible host.

---

## Getting Started

1. **Clone the repository:**
   ```sh
   git clone https://github.com/PrateekKumar15/Silque.git
   cd Silque
   ```
2. **Install backend dependencies:**
   ```sh
   npm install
   ```
3. **Install frontend dependencies:**
   ```sh
   cd frontend
   npm install
   cd ..
   ```
4. **Environment variables:**
   - Copy `.env.example` to `.env` and fill in your secrets (MongoDB URI, JWT secrets, Stripe keys, etc.)
5. **Run the backend server:**
   ```sh
   npm run dev
   ```
6. **Run the frontend (in a new terminal):**
   ```sh
   cd frontend
   npm run dev
   ```

---

## License

This project is licensed under the ISC License.
