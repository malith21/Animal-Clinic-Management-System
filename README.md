# 🏥 Veterinary Clinic Management System

<div align="center">

![Veterinary Clinic](https://img.shields.io/badge/Veterinary-Clinic-blue?style=for-the-badge)
![MERN Stack](https://img.shields.io/badge/MERN-Stack-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-ISC-yellow?style=for-the-badge)

**A comprehensive full-stack web application for managing veterinary clinic operations**

[Features](#-features) • [Tech Stack](#-tech-stack) • [Installation](#-installation) • [API Endpoints](#-api-endpoints) • [Contributing](#-contributing)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Environment Variables](#-environment-variables)
- [API Endpoints](#-api-endpoints)
- [Usage](#-usage)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

The **Veterinary Clinic Management System** is a modern, full-stack MERN application designed to streamline and automate veterinary clinic operations. This comprehensive system handles everything from pet registration and appointment scheduling to medical records management, inventory tracking, and payment processing.

### Why This System?

- **Efficient Patient Management**: Keep detailed records of pets and their owners
- **Streamlined Appointments**: Easy scheduling and management of veterinary appointments
- **Medical Records**: Comprehensive health records, prescriptions, vaccinations, and lab results
- **Inventory Control**: Track medical supplies and equipment
- **Payment Integration**: Secure payment processing with Stripe
- **Staff Management**: Manage clinic employees and system users
- **Report Generation**: Generate PDF reports for medical records and invoices

---

## ✨ Features

### 🐾 Pet & Owner Management
- Register and manage pet profiles
- Track pet owner information
- Maintain comprehensive pet health history
- Search and filter pet records

### 📅 Appointment System
- Schedule veterinary appointments
- Manage appointment status (pending, confirmed, completed, cancelled)
- View appointment calendar
- Send appointment reminders

### 🏥 Medical Records Management
- Create and maintain detailed medical records
- Track prescriptions and medications
- Record vaccination history
- Store laboratory test results
- Upload and attach medical documents/images
- Sequential record numbering system

### 💊 Prescription & Medication Tracking
- Digital prescription management
- Medication dosage and frequency tracking
- Prescription history for each pet
- Drug interaction warnings

### 💉 Vaccination Management
- Track vaccination schedules
- Record vaccination dates and types
- Send vaccination reminders
- Maintain vaccination certificates

### 🔬 Laboratory Results
- Store lab test results
- Attach lab reports and images
- Track test history
- Generate lab result PDFs

### 📦 Inventory Management
- Track medical supplies and equipment
- Monitor stock levels
- Set reorder points
- Inventory payment processing
- Generate inventory reports

### 👥 Employee & User Management
- Manage clinic staff profiles
- Role-based access control
- System user authentication
- Employee scheduling

### 💳 Payment Processing
- Secure payment integration with Stripe
- Process appointment payments
- Inventory purchase payments
- Generate invoices and receipts
- Payment history tracking

### 📊 Reporting & Analytics
- Generate PDF reports for medical records
- Create vaccination certificates
- Export lab results
- Financial reports
- Inventory reports

---

## 🛠️ Tech Stack

### Frontend
- **React.js** - Modern UI library
- **React Router** - Client-side routing
- **React Responsive Carousel** - Image carousels
- **Stripe React Components** - Payment UI
- **jsPDF** - PDF generation
- **jsPDF AutoTable** - Table generation in PDFs

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling

### Additional Libraries & Tools
- **Stripe** - Payment processing
- **Multer** - File upload handling
- **PDFKit** - PDF document generation
- **CORS** - Cross-origin resource sharing
- **Body Parser** - Request body parsing
- **Dotenv** - Environment variable management
- **Nodemon** - Development auto-reload

---

## 📁 Project Structure

```
veterinary-clinic-management/
│
├── frontend/                      # React frontend application
│   ├── ui/                       # UI components and pages
│   └── package.json              # Frontend dependencies
│
├── backend/                      # Node.js backend application
│   ├── config/                   # Configuration files
│   │   └── db.js                # Database connection
│   ├── models/                   # Mongoose models
│   │   ├── recordModel.js       # Medical records
│   │   ├── prescriptionModel.js # Prescriptions
│   │   ├── vaccinationModel.js  # Vaccinations
│   │   ├── labResultModel.js    # Lab results
│   │   └── ...                  # Other models
│   ├── routes/                   # API routes
│   │   ├── employees.js         # Employee management
│   │   ├── pets.js              # Pet management
│   │   ├── appointments.js      # Appointment system
│   │   ├── inventory.js         # Inventory management
│   │   ├── recordRoutes.js      # Medical records
│   │   ├── prescriptionRoutes.js
│   │   ├── vaccinationRoutes.js
│   │   ├── labResultRoutes.js
│   │   ├── StripeRouter.js      # Payment processing
│   │   ├── users.js             # User management
│   │   └── ...                  # Other routes
│   ├── utils/                    # Utility functions
│   │   ├── getNextSeq.js        # Sequential numbering
│   │   └── cascadeDeleteByRecordId.js
│   ├── uploads/                  # Uploaded files storage
│   ├── index.js                 # Application entry point
│   └── package.json             # Backend dependencies
│
├── .env                          # Environment variables
├── .gitignore                   # Git ignore rules
└── README.md                    # Project documentation
```

---

## 🚀 Installation

### Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v18 or higher)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas account)
- **Git**

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd veterinary-clinic-management
```

### Step 2: Backend Setup

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create .env file
cp .env.example .env

# Edit .env file with your configuration
nano .env
```

### Step 3: Frontend Setup

```bash
# Navigate to frontend directory
cd ../frontend

# Install dependencies
npm install

# Or install UI dependencies directly
npm run install-ui
```

### Step 4: Database Setup

1. **Local MongoDB**: Make sure MongoDB is running on your machine
   ```bash
   mongod
   ```

2. **MongoDB Atlas**: 
   - Create a free account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
   - Create a new cluster
   - Get your connection string
   - Add it to your `.env` file

### Step 5: Run the Application

#### Development Mode

**Terminal 1 - Backend:**
```bash
cd backend
npm start
```

**Terminal 2 - Frontend:**
```bash
cd frontend
npm run dev
```

#### Production Build

```bash
# Build frontend
cd frontend
npm run build

# Serve production build with backend
cd ../backend
npm start
```

---

## 🔐 Environment Variables

Create a `.env` file in the backend directory with the following variables:

```env
# Server Configuration
PORT=3000
NODE_ENV=development

# Database
MONGODB_URI=mongodb://localhost:27017/vet_clinic
# Or for MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/vet_clinic

# Frontend URL
CLIENT_URL=http://localhost:5173

# Stripe Payment
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key

# File Upload
MAX_FILE_SIZE=10485760  # 10MB in bytes
UPLOAD_DIR=./uploads

# JWT (if using authentication)
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=7d

# Email (if using email notifications)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_email_password
```

---

## 📡 API Endpoints

### Medical Records
```
GET    /api/records              # Get all records
GET    /api/records/:id          # Get record by ID
POST   /api/records              # Create new record
PUT    /api/records/:id          # Update record
DELETE /api/records/:id          # Delete record
```

### Prescriptions
```
GET    /api/prescriptions        # Get all prescriptions
GET    /api/prescriptions/:id    # Get prescription by ID
POST   /api/prescriptions        # Create prescription
PUT    /api/prescriptions/:id    # Update prescription
DELETE /api/prescriptions/:id    # Delete prescription
```

### Vaccinations
```
GET    /api/vaccinations         # Get all vaccinations
GET    /api/vaccinations/:id     # Get vaccination by ID
POST   /api/vaccinations         # Create vaccination
PUT    /api/vaccinations/:id     # Update vaccination
DELETE /api/vaccinations/:id     # Delete vaccination
```

### Lab Results
```
GET    /api/labresults           # Get all lab results
GET    /api/labresults/:id       # Get lab result by ID
POST   /api/labresults           # Create lab result
PUT    /api/labresults/:id       # Update lab result
DELETE /api/labresults/:id       # Delete lab result
```

### Pets
```
GET    /api/pets                 # Get all pets
GET    /api/pets/:id             # Get pet by ID
POST   /api/pets                 # Register new pet
PUT    /api/pets/:id             # Update pet info
DELETE /api/pets/:id             # Delete pet
```

### Appointments
```
GET    /api/appointments         # Get all appointments
GET    /api/appointments/:id     # Get appointment by ID
POST   /api/appointments         # Create appointment
PUT    /api/appointments/:id     # Update appointment
DELETE /api/appointments/:id     # Cancel appointment
```

### Inventory
```
GET    /api/inventory            # Get all items
GET    /api/inventory/:id        # Get item by ID
POST   /api/inventory            # Add new item
PUT    /api/inventory/:id        # Update item
DELETE /api/inventory/:id        # Delete item
```

### Employees
```
GET    /api/employees            # Get all employees
GET    /api/employees/:id        # Get employee by ID
POST   /api/employees            # Add new employee
PUT    /api/employees/:id        # Update employee
DELETE /api/employees/:id        # Delete employee
```

### Users & Authentication
```
GET    /api/users                # Get all users
GET    /api/systemusers          # Get system users
POST   /api/users/register       # Register user
POST   /api/users/login          # User login
```

### Sessions
```
GET    /api/sessions             # Get all sessions
POST   /api/sessions             # Create session
DELETE /api/sessions/:id         # End session
```

### Payments (Stripe)
```
POST   /api/stripe/create-payment-intent    # Create payment
POST   /api/stripe/confirm-payment          # Confirm payment
GET    /api/stripe/payment-history          # Get payment history
```

### Inventory Payments
```
GET    /api/inventorypayments    # Get all inventory payments
POST   /api/inventorypayments    # Create payment
```

### File Uploads
```
POST   /api/uploads              # Upload file
GET    /uploads/:filename        # Access uploaded file
```

---

## 💻 Usage

### Starting the Application

1. **Start MongoDB** (if using local installation)
   ```bash
   mongod
   ```

2. **Start Backend Server**
   ```bash
   cd backend
   npm start
   ```
   The backend will run on `http://localhost:3000`

3. **Start Frontend Development Server**
   ```bash
   cd frontend
   npm run dev
   ```
   The frontend will run on `http://localhost:5173`

4. **Access the Application**
   - Open your browser and navigate to `http://localhost:5173`

### Common Operations

#### Register a New Pet
1. Navigate to Pet Management
2. Click "Add New Pet"
3. Fill in pet and owner details
4. Submit the form

#### Create a Medical Record
1. Select a pet from the list
2. Click "Add Medical Record"
3. Enter diagnosis, treatment, and notes
4. Upload any supporting documents
5. Save the record

#### Schedule an Appointment
1. Go to Appointments
2. Click "New Appointment"
3. Select pet, date, time, and reason
4. Confirm the appointment

#### Process Payment
1. Navigate to the payment section
2. Enter payment details
3. Process through Stripe integration
4. Generate receipt/invoice

---

## 🧪 Testing

### Running Tests

```bash
# Backend tests
cd backend
npm test

# Frontend tests
cd frontend
npm test
```

### Test Coverage

```bash
# Generate coverage report
npm run test:coverage
```

---

## 🤝 Contributing

We welcome contributions to the Veterinary Clinic Management System! Here's how you can help:

### How to Contribute

1. **Fork the Repository**
   ```bash
   git clone https://github.com/your-username/vet-clinic-system.git
   ```

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **Make Your Changes**
   - Write clean, readable code
   - Follow existing code style
   - Add comments where necessary
   - Update documentation

4. **Commit Your Changes**
   ```bash
   git add .
   git commit -m "Add amazing feature"
   ```

5. **Push to Your Fork**
   ```bash
   git push origin feature/amazing-feature
   ```

6. **Open a Pull Request**
   - Provide a clear description of your changes
   - Reference any related issues
   - Wait for review

### Contribution Guidelines

- Follow the existing code structure
- Write meaningful commit messages
- Test your changes thoroughly
- Update documentation as needed
- Respect the code of conduct

---

## 🐛 Troubleshooting

### Common Issues

**Issue: MongoDB Connection Failed**
```
Solution: 
1. Check if MongoDB is running
2. Verify MONGODB_URI in .env
3. Check network connectivity
4. Ensure MongoDB Atlas IP whitelist includes your IP
```

**Issue: Port Already in Use**
```
Solution:
1. Change PORT in .env file
2. Or kill the process using the port:
   - Linux/Mac: lsof -ti:3000 | xargs kill
   - Windows: netstat -ano | findstr :3000
```

**Issue: Stripe Payment Not Working**
```
Solution:
1. Verify STRIPE_SECRET_KEY in .env
2. Check Stripe dashboard for errors
3. Ensure test mode is enabled for development
```

**Issue: File Upload Failing**
```
Solution:
1. Check UPLOAD_DIR exists
2. Verify file size is within MAX_FILE_SIZE
3. Ensure proper file permissions
```

---

## 📊 Database Schema

### Medical Records
```javascript
{
  recordId: String,          // Auto-generated sequential ID
  petId: ObjectId,          // Reference to Pet
  date: Date,
  diagnosis: String,
  treatment: String,
  notes: String,
  veterinarian: String,
  attachments: [String]     // File paths
}
```

### Prescriptions
```javascript
{
  recordId: ObjectId,       // Reference to Medical Record
  medication: String,
  dosage: String,
  frequency: String,
  duration: String,
  instructions: String
}
```

### Vaccinations
```javascript
{
  recordId: ObjectId,       // Reference to Medical Record
  vaccineName: String,
  dateAdministered: Date,
  nextDueDate: Date,
  veterinarian: String,
  batchNumber: String
}
```

---

## 📝 License

This project is licensed under the **ISC License**.

---

## 👥 Team

This project was developed as part of an academic initiative.

### Contributors
- **Medical Records Module** - Medical records, prescriptions, vaccinations, lab results
- **Appointment System** - Appointment scheduling and management
- **Inventory Management** - Stock tracking and payments
- **User Management** - Authentication and authorization
- **Payment Integration** - Stripe payment processing

---

## 📞 Support

For support, questions, or feedback:

- 📧 Email: support@vetclinic.com
- 🐛 Issues: [GitHub Issues](https://github.com/your-repo/issues)
- 💬 Discussions: [GitHub Discussions](https://github.com/your-repo/discussions)

---

## 🎓 Acknowledgments

- MongoDB for the excellent database solution
- Stripe for secure payment processing
- The MERN stack community for resources and support
- All contributors who helped build this system

---

## 🗺️ Roadmap

### Upcoming Features

- [ ] Mobile application (React Native)
- [ ] Email/SMS notifications
- [ ] Video consultation integration
- [ ] AI-powered diagnosis suggestions
- [ ] Advanced analytics dashboard
- [ ] Multi-language support
- [ ] Appointment reminder system
- [ ] Prescription auto-refill
- [ ] Client portal for pet owners
- [ ] Integration with veterinary labs

---

<div align="center">

**Made with ❤️ for Veterinary Professionals**

⭐ Star this repo if you find it helpful!

</div>

