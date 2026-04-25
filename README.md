# PropertyHub - Property Management Application

<div align="center">

![React](https://img.shields.io/badge/React-19.2.4-61DAFB?logo=react)
![Node.js](https://img.shields.io/badge/Node.js-18+-green?logo=node.js)
![MongoDB](https://img.shields.io/badge/MongoDB-7.1.1-47A248?logo=mongodb)
![Firebase](https://img.shields.io/badge/Firebase-12.4.0-FFCA28?logo=firebase)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-4.2.2-06B6D4?logo=tailwindcss)
![Express](https://img.shields.io/badge/Express-5.2.1-000000?logo=express)
![License](https://img.shields.io/badge/License-MIT-yellow)

**A comprehensive full-stack property management system for landlords and tenants**

[Features](#features) • [Tech Stack](#tech-stack) • [Installation](#installation) • [API Reference](#api-reference) • [Project Structure](#project-structure) • [Deployment](#deployment) • [License](LICENSE)

</div>

---

## Overview

PropertyHub is a complete property management solution that connects landlords with tenants. Landlords can list properties, manage bookings, track maintenance requests, and receive payments. Tenants can browse properties, book viewings, submit maintenance requests, and make rent payments through integrated payment gateways.

---

## Features

### 🔐 Authentication & Authorization

| Feature | Description |
|---------|-------------|
| Email/Password Auth | Traditional login with JWT tokens |
| Google OAuth | One-click sign-in with Google |
| Role-based Access | Separate dashboards for Admin, Landlord, Tenant |
| Protected Routes | Route guards based on user role |
| Session Management | Persistent login with secure token storage |

### 👤 Landlord Features

| Feature | Description |
|---------|-------------|
| Property Listing | Add, edit, delete property listings with images |
| Dashboard | Overview of properties, bookings, earnings |
| Tenant Management | View and manage tenant information |
| Maintenance Tracking | Handle repair requests from tenants |
| Payment Tracking | Monitor rent payments via Razorpay |
| Public Profile | Shareable profile page for landlords |
| Booking Management | Approve/reject property viewing requests |
| Earnings Analytics | View payment history and revenue |

### 🏠 Tenant Features

| Feature | Description |
|---------|-------------|
| Property Browse | Search and filter available properties |
| Property Details | View detailed property information |
| Book Viewings | Schedule property viewing appointments |
| Maintenance Requests | Submit and track repair requests |
| Payment History | View past payments and receipts |
| Profile Management | Update personal information |
| Support Tickets | Submit queries and support requests |
| Notifications | Real-time updates on bookings/requests |

### ⚙️ Admin Features

| Feature | Description |
|---------|-------------|
| User Management | View all users, approve landlords |
| Analytics Dashboard | Platform-wide statistics |
| Maintenance Oversight | Monitor all maintenance requests |
| Support Query Management | Handle tenant/landlord queries |
| Booking Reports | Platform booking statistics |
| Payment Reports | Overall payment analytics |

### 💳 Payments

| Feature | Description |
|---------|-------------|
| Razorpay Integration | Secure payment processing |
| Rent Payments | Monthly rent via online gateway |
| Payment Verification | Server-side payment validation |
| Payment History | Complete transaction records |

---

## Tech Stack

### Frontend (Client)

| Technology | Version | Purpose |
|------------|---------|---------|
| React | 19.2.4 | UI Framework |
| Vite | 8.0.1 | Build Tool |
| React Router | 7.13.2 | Client-side Routing |
| Tailwind CSS | 4.2.2 | Styling |
| Firebase | 12.4.0 | Authentication |
| Framer Motion | 12.38.0 | Animations |
| Recharts | 3.8.1 | Data Visualization |
| Axios | 1.14.0 | HTTP Client |
| Lucide React | 1.7.0 | Icons |
| React Hot Toast | 2.6.0 | Notifications |

### Backend (Server)

| Technology | Version | Purpose |
|------------|---------|---------|
| Node.js | 18+ | JavaScript Runtime |
| Express | 5.2.1 | Web Framework |
| MongoDB | 7.1.1 | Database |
| Mongoose | 9.3.3 | ODM |
| JWT | 9.0.3 | Authentication |
| bcryptjs | 3.0.2 | Password Hashing |
| Razorpay | 2.9.6 | Payments |
| Google Auth Library | 10.6.2 | OAuth |
| Nodemailer | 8.0.4 | Email |
| Firebase Functions | 6.6.0 | Serverless |
| Netlify Functions | - | Deployment |

---

## Installation

### Prerequisites

- Node.js 18 or higher
- MongoDB (local installation or Atlas cloud cluster)
- Firebase CLI (for deployment)
- Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/nehajaiswal230250/Property-app.git
cd Property-app
```

### Step 2: Install Dependencies

**Server dependencies:**
```bash
cd server
npm install
```

**Client dependencies:**
```bash
cd client
npm install
```

### Step 3: Environment Setup

**Server Environment** - Create a file named `.env` in the `/server` directory:

```env
# Server Configuration
PORT=5000

# MongoDB Connection
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/dbname
# OR for direct connection
MONGO_DIRECT_URI=mongodb://host1:27017,host2:27017/dbname

# JWT Authentication
JWT_SECRET=your-super-secret-jwt-key-change-in-production
JWT_EXPIRES_IN=7d

# Razorpay Payment Gateway
RAZORPAY_KEY_ID=your-razorpay-key-id
RAZORPAY_SECRET=your-razorpay-secret

# Google OAuth
GOOGLE_CLIENT_ID=your-google-client-id.apps.googleusercontent.com
GOOGLE_CLIENT_SECRET=your-google-client-secret

# Firebase (for server-side token verification)
FIREBASE_API_KEY=your-firebase-api-key

# Admin Configuration
ADMIN_EMAIL=admin@example.com

# Email Notifications (Nodemailer)
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-specific-password
```

**Client Environment** - Create a file named `.env` in the `/client` directory:

```env
# API Configuration
VITE_API_URL=http://localhost:5000

# Firebase Configuration
VITE_FIREBASE_API_KEY=your-api-key
VITE_FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your-project-id
VITE_FIREBASE_STORAGE_BUCKET=your-project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your-sender-id
VITE_FIREBASE_APP_ID=your-app-id

# Google OAuth (Client-side)
VITE_GOOGLE_CLIENT_ID=your-google-client-id.apps.googleusercontent.com
```

### Step 4: Firebase Setup

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project
3. Enable **Authentication** → Sign-in Methods:
   - Email/Password
   - Google
4. Copy Firebase config to client `.env`

### Step 5: MongoDB Setup

1. Create account at [MongoDB Atlas](https://www.mongodb.com/atlas)
2. Create a cluster (free tier available)
3. Create database user
4. Get connection string
5. Update `MONGODB_URI` in server `.env`

### Step 6: Run the Application

**Development mode:**

Terminal 1 - Start Server:
```bash
cd server
npm run serve
```

Terminal 2 - Start Client:
```bash
cd client
npm run dev
```

Access the application at `http://localhost:5173`

**Production Build:**

```bash
cd client
npm run build
```

---

## API Reference

### Authentication Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | User registration |
| POST | `/api/auth/login` | User login with JWT |
| POST | `/api/auth/google` | Google OAuth login |
| POST | `/api/auth/firebase-login` | Firebase token verification |
| GET | `/api/auth/me` | Get current user profile |
| PUT | `/api/auth/profile` | Update user profile |

### Property Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/properties` | List all properties |
| GET | `/api/properties/:id` | Get property details |
| POST | `/api/properties` | Create new property (Landlord) |
| PUT | `/api/properties/:id` | Update property |
| DELETE | `/api/properties/:id` | Delete property |
| GET | `/api/properties/user/:userId` | Get properties by landlord |

### Booking Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/bookings` | Create booking request |
| GET | `/api/bookings/my` | Get user's bookings |
| GET | `/api/bookings/property/:propertyId` | Get property bookings |
| PUT | `/api/bookings/:id` | Update booking status |
| DELETE | `/api/bookings/:id` | Cancel booking |

### Maintenance Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/maintenance` | Create maintenance request |
| GET | `/api/maintenance` | List all maintenance requests |
| GET | `/api/maintenance/user` | Get user's requests |
| PUT | `/api/maintenance/:id` | Update request status |
| DELETE | `/api/maintenance/:id` | Delete request |

### Payment Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/payments/create-order` | Create Razorpay order |
| POST | `/api/payments/verify` | Verify payment signature |
| GET | `/api/payments/history` | Get payment history |
| GET | `/api/payments/user/:userId` | Get user payments |

---

## Project Structure

```
Property-app/
├── client/                         # React Frontend
│   ├── src/
│   │   ├── components/            # Reusable UI Components
│   │   │   ├── admin/             # Admin-specific components
│   │   │   ├── auth/              # Authentication components
│   │   │   ├── common/            # Shared components
│   │   │   ├── landlord/          # Landlord-specific components
│   │   │   └── tenant/            # Tenant-specific components
│   │   ├── pages/                 # Page Components
│   │   │   ├── AdminDashboard.jsx
│   │   │   ├── AdminMaintenance.jsx
│   │   │   ├── AdminQueries.jsx
│   │   │   ├── AdminUsers.jsx
│   │   │   ├── CompleteProfile.jsx
│   │   │   ├── Contact.jsx
│   │   │   ├── Dashboard.jsx      # Landlord Dashboard
│   │   │   ├── LandlordMaintenance.jsx
│   │   │   ├── LandlordProfile.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Payments.jsx
│   │   │   ├── PublicProfile.jsx
│   │   │   ├── Queries.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── TenantBookings.jsx
│   │   │   ├── TenantBrowse.jsx
│   │   │   ├── TenantDashboard.jsx
│   │   │   ├── TenantMaintenance.jsx
│   │   │   ├── TenantNotifications.jsx
│   │   │   ├── TenantProfile.jsx
│   │   │   ├── TenantPropertyDetails.jsx
│   │   │   └── TenantSupport.jsx
│   │   ├── services/              # API Service Layer
│   │   │   ├── maintenanceService.js
│   │   │   ├── profileService.js
│   │   │   └── propertyBookingService.js
│   │   ├── utils/                  # Utility Functions
│   │   │   └── sessionUser.js
│   │   ├── App.jsx                # Main App Component
│   │   ├── firebase.js           # Firebase Configuration
│   │   ├── index.css              # Global Styles
│   │   └── main.jsx               # Entry Point
│   ├── public/                     # Static Assets
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
│
├── server/                          # Express Backend
│   ├── middleware/
│   │   └── auth.js                # JWT Auth Middleware
│   ├── models/                     # Mongoose Models
│   │   ├── booking.js
│   │   ├── maintenance.js
│   │   ├── payment.js
│   │   ├── property.js
│   │   └── user.js
│   ├── netlify/
│   │   └── functions/
│   │       └── api.js             # Netlify Function Handler
│   ├── scripts/
│   │   └── cleanupDuplicateRentData.js
│   ├── uploads/                    # File Uploads
│   │   └── profile-images/
│   ├── index.js                   # Firebase Functions Handler
│   ├── server.js                  # Main Server File
│   └── package.json
│
├── firebase.json                   # Firebase Configuration
├── firestore.rules                # Firestore Security Rules
├── netlify.toml                   # Netlify Deployment Config
├── .gitignore                     # Git Ignore Patterns
├── README.md                      # Project Documentation
├── LICENSE                        # MIT License
└── CONTRIBUTING.md                # Contribution Guidelines
```

---

## Data Models

### User Model

```javascript
{
  name: String,
  email: String (unique),
  phone: String,
  password: String (hashed),
  role: "admin" | "landlord" | "tenant",
  isApproved: Boolean,
  propertyName: String,
  propertyLocation: String,
  propertyImage: String,
  propertyPrice: Number,
  propertyFacilities: [String],
  profileImage: String,
  createdAt: Date
}
```

### Property Model

```javascript
{
  owner: ObjectId (ref: User),
  name: String,
  location: String,
  price: Number,
  image: String,
  facilities: [String],
  description: String,
  isAvailable: Boolean,
  createdAt: Date
}
```

### Booking Model

```javascript
{
  property: ObjectId (ref: Property),
  tenant: ObjectId (ref: User),
  landlord: ObjectId (ref: User),
  status: "pending" | "approved" | "rejected",
  date: Date,
  message: String,
  createdAt: Date
}
```

### Maintenance Model

```javascript
{
  property: ObjectId (ref: Property),
  tenant: ObjectId (ref: User),
  landlord: ObjectId (ref: User),
  issue: String,
  description: String,
  status: "pending" | "in-progress" | "resolved",
  createdAt: Date
}
```

### Payment Model

```javascript
{
  user: ObjectId (ref: User),
  amount: Number,
  razorpayId: String,
  status: "pending" | "completed" | "failed",
  type: "rent" | "deposit" | "other",
  createdAt: Date
}
```

---

## Deployment

### Firebase Functions

```bash
cd server
npm run deploy
```

### Netlify

The project includes `netlify.toml` for automatic deployment:

1. Push to GitHub
2. Connect repository to Netlify
3. Automatic deployment on every push

### Manual Deployment

```bash
# Build client
cd client
npm run build

# Deploy to Firebase
cd server
firebase deploy --only functions
```

---

## Environment Variables Reference

| Variable | Description | Required |
|----------|-------------|----------|
| `PORT` | Server port | Yes |
| `MONGODB_URI` | MongoDB connection string | Yes |
| `JWT_SECRET` | Secret for JWT signing | Yes |
| `RAZORPAY_KEY_ID` | Razorpay API key | Yes (payments) |
| `RAZORPAY_SECRET` | Razorpay API secret | Yes (payments) |
| `GOOGLE_CLIENT_ID` | Google OAuth client ID | Yes (Google login) |
| `GOOGLE_CLIENT_SECRET` | Google OAuth secret | Yes (Google login) |
| `FIREBASE_API_KEY` | Firebase API key | Yes (Firebase auth) |
| `EMAIL_USER` | Gmail for notifications | No |
| `EMAIL_PASS` | Gmail app password | No |

---

## Security Features

- **Password Hashing**: bcrypt with salt rounds
- **JWT Tokens**: Signed with secret, configurable expiry
- **Input Validation**: Server-side validation on all inputs
- **CORS**: Configured for controlled access
- **Protected Routes**: Server-side role verification
- **Payment Verification**: Server-side Razorpay signature validation

---

## Troubleshooting

### Common Issues

**MongoDB Connection Failed**
```
- Check network/firewall settings
- Try replacing mongodb+srv with direct mongodb:// URI
- Verify username/password in connection string
```

**Firebase Auth Issues**
```
- Verify Firebase config in client .env
- Enable required sign-in methods in Firebase Console
- Check API key restrictions
```

**Payment Gateway Issues**
```
- Verify Razorpay keys are correct
- Check webhook configuration
- Ensure server is accessible for webhook callbacks
```

---

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

---

## Author

**Neha Jaiswal**

- GitHub: [@nehajaiswal230250](https://github.com/nehajaiswal230250)

---

<div align="center">
⭐ Star this repository if you found it helpful!
</div>
