# 🏨 Luxury Resort Website

A full-stack, modern resort booking website application featuring a dynamic React frontend and Express.js backend with MongoDB integration.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [API Documentation](#api-documentation)
- [Project Components](#project-components)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 Overview

This project is a comprehensive resort management and booking platform designed to showcase luxury accommodations, experiences, and facilitate guest inquiries. The application provides a seamless user experience with a responsive frontend and robust backend API for managing reservations and communications.

---

## ✨ Features

### Frontend Features
- **Responsive Design** - Mobile-first approach using Tailwind CSS
- **Room Showcase** - Interactive room gallery with detailed information
- **Room Details** - Comprehensive room specifications, amenities, and image galleries
- **Experiences** - Featured activities and services offered at the resort
- **Gallery** - Visual showcase of resort facilities and amenities
- **Contact Form** - Direct inquiry submission system
- **Testimonials** - Guest reviews carousel
- **Smooth Navigation** - Fast page transitions with React Router
- **Image Lightbox** - Interactive image preview functionality

### Backend Features
- **RESTful API** - Well-structured API endpoints
- **Email Notifications** - Automated email service for inquiries
- **MongoDB Database** - Persistent data storage
- **CORS Support** - Secure cross-origin resource sharing
- **Error Handling** - Comprehensive error management
- **Environment Variables** - Secure configuration management
- **Health Check** - Server status monitoring endpoint

---

## 🛠️ Tech Stack

### Frontend
| Technology | Version | Purpose |
|------------|---------|---------|
| React | 18.2.0 | UI Library |
| Vite | 5.0.8 | Build Tool & Dev Server |
| React Router | 6.20.0 | Client-side Routing |
| Tailwind CSS | 3.3.6 | CSS Framework |
| PostCSS | 8.4.32 | CSS Processing |

### Backend
| Technology | Version | Purpose |
|------------|---------|---------|
| Node.js | - | Runtime Environment |
| Express | 4.18.2 | Web Framework |
| MongoDB | - | Database |
| Mongoose | 8.0.3 | MongoDB ODM |
| Nodemailer | 6.9.7 | Email Service |
| CORS | 2.8.5 | Cross-Origin Support |
| Dotenv | 16.3.1 | Environment Config |

---

## 📁 Project Structure

```
Resort-website-main/
├── index.html                 # Entry HTML file
├── package.json              # Frontend dependencies
├── vite.config.js            # Vite configuration
├── tailwind.config.js        # Tailwind CSS setup
├── postcss.config.js         # PostCSS configuration
│
├── src/                       # Frontend source code
│   ├── App.jsx               # Root React component
│   ├── main.jsx              # React entry point
│   ├── index.css             # Global styles
│   ├── ScrollToTop.jsx       # Scroll behavior component
│   ├── components/           # Reusable React components
│   │   ├── Navbar.jsx        # Navigation bar
│   │   ├── Footer.jsx        # Footer component
│   │   ├── RoomCard.jsx      # Room display card
│   │   ├── Lightbox.jsx      # Image gallery lightbox
│   │   └── TestimonialCarousel.jsx # Reviews carousel
│   ├── pages/                # Page components
│   │   ├── Home.jsx          # Landing page
│   │   ├── About.jsx         # About page
│   │   ├── Rooms.jsx         # Rooms listing page
│   │   ├── RoomDetails.jsx   # Individual room details
│   │   ├── Experiences.jsx   # Activities/experiences
│   │   ├── Gallery.jsx       # Image gallery
│   │   └── Contact.jsx       # Contact/inquiry form
│   ├── data/
│   │   └── data.json         # Static resort data (rooms, amenities)
│   └── utils/
│       ├── api.js            # API client helper
│       └── hooks.js          # Custom React hooks
│
├── Backend/                   # Backend source code
│   ├── package.json          # Backend dependencies
│   ├── server.js             # Express server entry point
│   ├── models/
│   │   └── Enquiry.js        # MongoDB enquiry schema
│   ├── routes/
│   │   └── enquiry.js        # Enquiry API routes
│   └── utils/
│       └── emailService.js   # Email sending service
│
└── README.md                 # Project documentation

```

---

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v14.0.0 or higher) - [Download](https://nodejs.org/)
- **npm** (v6.0.0 or higher) - Comes with Node.js
- **MongoDB** (Local or Cloud Atlas instance) - [Download](https://www.mongodb.com/)
- **Git** - [Download](https://git-scm.com/)
- A **Code Editor** (VS Code recommended) - [Download](https://code.visualstudio.com/)

---

## 🚀 Installation & Setup

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd Resort-website-main
```

### Step 2: Frontend Setup

```bash
# Install frontend dependencies
npm install

# Install Tailwind CSS and dependencies (if not already included)
npm install -D tailwindcss postcss autoprefixer
```

### Step 3: Backend Setup

```bash
# Navigate to backend directory
cd Backend

# Install backend dependencies
npm install
```

### Step 4: Environment Configuration

Create a `.env` file in the `Backend/` directory:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# MongoDB Configuration
MONGO_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/<database>?retryWrites=true&w=majority

# Client URL
CLIENT_URL=http://localhost:3000

# Email Configuration (Gmail or your email service)
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-password
EMAIL_SERVICE=gmail

# Resort Contact Email
RESORT_EMAIL=contact@resort.com
```

**Gmail App Password Setup:**
1. Enable 2-Factor Authentication on your Gmail account
2. Go to [Google App Passwords](https://myaccount.google.com/apppasswords)
3. Generate an app password for Gmail
4. Use this password for `EMAIL_PASS`

---

## ⚙️ Configuration

### Frontend Configuration

**Vite Configuration** (`vite.config.js`):
- Frontend runs on `localhost:3000` by default
- React plugin enabled for JSX support

**Tailwind CSS** (`tailwind.config.js`):
- Scans `src/` directory for class names
- Pre-configured dark mode support

### Backend Configuration

**Environment Variables:**
- `MONGO_URI`: MongoDB connection string (Atlas or local)
- `PORT`: Server port (default: 5000)
- `CLIENT_URL`: Frontend URL for CORS
- `EMAIL_*`: Email service credentials

**MongoDB Connection:**
- Uses Mongoose for schema validation
- Connection error handling implemented
- Auto-reconnect enabled

---

## ▶️ Running the Application

### Option 1: Run in Separate Terminals (Recommended for Development)

**Terminal 1 - Frontend:**
```bash
npm run dev
```
- Frontend available at: `http://localhost:3000`
- Vite dev server with hot reload enabled

**Terminal 2 - Backend:**
```bash
cd Backend
npm run dev
```
- Backend API available at: `http://localhost:5000`
- Uses `--watch` flag for auto-restart on changes

### Option 2: Run Using npm Scripts

**Build for Production:**
```bash
# Frontend
npm run build

# Backend doesn't require build (Node/ES modules)
```

**Preview Production Build:**
```bash
npm run preview
```

### Option 3: Using Concurrently (Run Both in One Terminal)

Install concurrently:
```bash
npm install -D concurrently
```

Add to root `package.json`:
```json
{
  "scripts": {
    "dev": "concurrently \"npm run dev\" \"cd Backend && npm run dev\""
  }
}
```

Then run:
```bash
npm run dev
```

---

## 📡 API Documentation

### Base URL
```
http://localhost:5000/api
```

### Endpoints

#### 1. Health Check
```http
GET /health
```
**Response:**
```json
{
  "message": "Server is running"
}
```

#### 2. Submit Room Inquiry
```http
POST /api/enquiry
```
**Request Body:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "+1234567890",
  "roomType": "Ocean View Suite",
  "checkIn": "2024-06-15",
  "checkOut": "2024-06-18",
  "guests": 2,
  "message": "Special requests here"
}
```

**Response (Success - 201):**
```json
{
  "success": true,
  "message": "Enquiry submitted successfully",
  "enquiryId": "507f1f77bcf86cd799439011"
}
```

**Response (Error - 400):**
```json
{
  "error": "Validation error message"
}
```

### CORS Configuration
- **Allowed Origins:** `http://localhost:3000` (or `CLIENT_URL` env variable)
- **Allowed Methods:** GET, POST, PUT, DELETE
- **Credentials:** Enabled

---

## 🎨 Project Components

### Frontend Components

| Component | Purpose | Location |
|-----------|---------|----------|
| `Navbar` | Navigation header | `src/components/Navbar.jsx` |
| `Footer` | Footer section | `src/components/Footer.jsx` |
| `RoomCard` | Room display card | `src/components/RoomCard.jsx` |
| `Lightbox` | Image modal gallery | `src/components/Lightbox.jsx` |
| `TestimonialCarousel` | Reviews slider | `src/components/TestimonialCarousel.jsx` |
| `ScrollToTop` | Auto-scroll on route change | `src/ScrollToTop.jsx` |

### Frontend Pages

| Page | Route | Purpose |
|------|-------|---------|
| Home | `/` | Landing page with hero & features |
| About | `/about` | Resort information & history |
| Rooms | `/rooms` | All available rooms listing |
| Room Details | `/rooms/:id` | Detailed room information |
| Experiences | `/experiences` | Activities & services showcase |
| Gallery | `/gallery` | Photo gallery |
| Contact | `/contact` | Inquiry form |

### Backend Models

**Enquiry Schema** (`Backend/models/Enquiry.js`):
```javascript
{
  name: String,
  email: String,
  phone: String,
  roomType: String,
  checkIn: Date,
  checkOut: Date,
  guests: Number,
  message: String,
  createdAt: Date (auto)
}
```

---

## 🌐 Deployment

### Frontend Deployment (Vercel/Netlify)

**Vercel:**
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

**Netlify:**
```bash
# Build
npm run build

# Deploy dist folder to Netlify
```

**Environment Variables for Production:**
Create a `.env.production` file with production API URL:
```env
VITE_API_URL=https://api.yourdomain.com
```

### Backend Deployment (Heroku/Railway)

**Railway:**
1. Push to GitHub
2. Connect repository to Railway
3. Add environment variables
4. Deploy automatically

**Heroku:**
```bash
# Login to Heroku
heroku login

# Create app
heroku create your-resort-api

# Set environment variables
heroku config:set MONGO_URI=<your-mongo-uri>
heroku config:set CLIENT_URL=https://your-frontend.vercel.app

# Deploy
git push heroku main
```

---

## 🐛 Troubleshooting

### Common Issues & Solutions

**Issue: MongoDB Connection Error**
```
Error: connect ECONNREFUSED 127.0.0.1:27017
```
**Solution:**
- Ensure MongoDB is running locally: `mongod`
- Or update `MONGO_URI` to use MongoDB Atlas cloud connection
- Check connection string format

**Issue: CORS Error**
```
Access to XMLHttpRequest blocked by CORS policy
```
**Solution:**
- Ensure `CLIENT_URL` environment variable is correctly set
- Verify frontend is running on the correct port
- Check CORS middleware in `server.js`

**Issue: Email Not Sending**
```
Error: Invalid login: 535-5.7.8 Username and password not accepted
```
**Solution:**
- Use Gmail App Password (not regular password)
- Enable 2FA on Gmail account
- Check credentials in `.env` file

**Issue: Vite Dev Server Not Opening**
```
Port 3000 already in use
```
**Solution:**
```bash
# Kill process on port 3000 (Windows)
netstat -ano | findstr :3000
taskkill /PID <PID> /F

# Or change port in vite.config.js
```

**Issue: Dependencies Installation Error**
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

---

## 👥 Contributing

### Development Workflow

1. Create a new branch:
```bash
git checkout -b feature/your-feature-name
```

2. Make changes and commit:
```bash
git add .
git commit -m "feat: add your feature description"
```

3. Push to repository:
```bash
git push origin feature/your-feature-name
```

4. Create a Pull Request

### Code Style Guidelines

- Use **ES6+ syntax** (arrow functions, const/let, template literals)
- **Indent:** 2 spaces
- **Naming:** camelCase for variables/functions, PascalCase for components
- **Comments:** Add comments for complex logic
- **Testing:** Test features before committing

---

## 📝 License

This project is licensed under the **MIT License** - see the LICENSE file for details.

---

## 📞 Support & Contact

For issues, questions, or suggestions:

- **Email:** support@resort.com
- **GitHub Issues:** [Create an issue](https://github.com/yourrepo/issues)
- **Documentation:** Refer to component-specific README files

---

## 🙏 Acknowledgments

- Thanks to the React and Express communities
- Tailwind CSS for amazing utility-first framework
- MongoDB for flexible database solution

---

**Last Updated:** March 2024
**Version:** 1.0.0
**Status:** Production Ready ✅
#   R e s o r t - W e b s i t e - F r o n t e n d  
 