# ODD (Our Daily Dashboard) Project

A full-stack web application with a React frontend and Node.js/Express backend, featuring user authentication, dashboard functionality, and modern UI design.

## 🚀 Features

- **Frontend**: React.js with modern UI components
- **Backend**: Node.js/Express.js REST API
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JWT-based authentication system
- **Security**: Password hashing, CORS, input validation
- **User Management**: Registration, login, profile management
- **Role-based Access**: User and Admin roles

## 📁 Project Structure

```
oddo/
├── frontend/          # React frontend application
├── backend/           # Node.js/Express backend API
├── .gitignore         # Git ignore rules
└── README.md          # Project documentation
```

## 🛠️ Prerequisites

- Node.js (v14 or higher)
- MongoDB (local or cloud instance)
- npm or yarn
- Git

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone <your-repository-url>
cd oddo
```

### 2. Backend Setup
```bash
cd backend
npm install
cp env.example .env
# Edit .env with your configuration
npm run dev
```

### 3. Frontend Setup
```bash
cd frontend
npm install
npm start
```

## 📋 Backend API

The backend runs on `http://localhost:5000` and provides the following endpoints:

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user

### Users
- `GET /api/users` - Get all users (admin)
- `GET /api/users/:id` - Get user by ID
- `PUT /api/users/profile` - Update profile
- `DELETE /api/users/:id` - Delete user (admin)

### General
- `GET /` - Welcome message
- `GET /health` - Health check

## 🔧 Configuration

### Backend Environment Variables
Create a `.env` file in the `backend/` directory:

```env
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/oddo
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
CORS_ORIGIN=http://localhost:3000
```

## 🏃‍♂️ Running the Application

### Development Mode

**Backend:**
```bash
cd backend
npm run dev
```

**Frontend:**
```bash
cd frontend
npm start
```

### Production Mode

**Backend:**
```bash
cd backend
npm start
```

**Frontend:**
```bash
cd frontend
npm run build
```

## 🔐 Authentication

The application uses JWT (JSON Web Tokens) for authentication. Include the token in API requests:

```
Authorization: Bearer <your-jwt-token>
```

## 🗄️ Database Schema

### User Model
- `username` (String, unique)
- `email` (String, unique)
- `password` (String, hashed)
- `firstName` (String)
- `lastName` (String)
- `role` (String: 'user' | 'admin')
- `isActive` (Boolean)
- `lastLogin` (Date)
- `createdAt` (Date)
- `updatedAt` (Date)

## 🛡️ Security Features

- Password hashing with bcrypt
- JWT token expiration
- CORS configuration
- Input validation
- Role-based access control
- Environment variable protection

## 🧪 Testing

### Backend Testing
```bash
cd backend
npm test
```

### Frontend Testing
```bash
cd frontend
npm test
```

## 📦 Deployment

### Backend Deployment
1. Set up environment variables
2. Build the application
3. Deploy to your preferred hosting service

### Frontend Deployment
1. Build the application: `npm run build`
2. Deploy the `build/` folder to your hosting service

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Test thoroughly
5. Commit your changes: `git commit -m 'Add feature'`
6. Push to the branch: `git push origin feature-name`
7. Submit a pull request

## 📝 License

This project is licensed under the ISC License.

## 📞 Support

For support and questions, please open an issue in the repository or contact the development team.

## 🔄 Version History

- **v1.0.0** - Initial release with basic authentication and user management 