# ODD Backend API

A Node.js/Express.js backend API for the ODD application with MongoDB database and JWT authentication.

## Features

- User authentication (register, login, logout)
- JWT token-based authorization
- User management (CRUD operations)
- Role-based access control (User/Admin)
- MongoDB database integration
- Password hashing with bcrypt
- CORS enabled for frontend integration

## Prerequisites

- Node.js (v14 or higher)
- MongoDB (local or cloud instance)
- npm or yarn

## Installation

1. Clone the repository
2. Navigate to the backend directory:
   ```bash
   cd backend
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

4. Create a `.env` file based on `env.example`:
   ```bash
   cp env.example .env
   ```

5. Update the `.env` file with your configuration:
   ```env
   PORT=5000
   NODE_ENV=development
   MONGODB_URI=mongodb://localhost:27017/oddo
   JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
   CORS_ORIGIN=http://localhost:3000
   ```

## Running the Application

### Development Mode
```bash
npm run dev
```

### Production Mode
```bash
npm start
```

The server will start on `http://localhost:5000` (or the port specified in your `.env` file).

## API Endpoints

### Authentication Routes

#### POST `/api/auth/register`
Register a new user
```json
{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "password123",
  "firstName": "John",
  "lastName": "Doe"
}
```

#### POST `/api/auth/login`
Login user
```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

#### GET `/api/auth/me`
Get current user profile (requires authentication)

### User Routes

#### GET `/api/users`
Get all users (admin only)

#### GET `/api/users/:id`
Get user by ID (requires authentication)

#### PUT `/api/users/profile`
Update user profile (requires authentication)
```json
{
  "firstName": "John",
  "lastName": "Smith",
  "email": "john.smith@example.com"
}
```

#### DELETE `/api/users/:id`
Delete user (admin only)

### General Routes

#### GET `/`
Welcome message

#### GET `/health`
Health check endpoint

## Authentication

The API uses JWT (JSON Web Tokens) for authentication. Include the token in the Authorization header:

```
Authorization: Bearer <your-jwt-token>
```

## Database Schema

### User Model
- `username` (String, required, unique)
- `email` (String, required, unique)
- `password` (String, required, hashed)
- `firstName` (String, required)
- `lastName` (String, required)
- `role` (String, enum: ['user', 'admin'], default: 'user')
- `isActive` (Boolean, default: true)
- `lastLogin` (Date)
- `createdAt` (Date, auto-generated)
- `updatedAt` (Date, auto-generated)

## Error Handling

The API returns appropriate HTTP status codes and error messages:

- `200` - Success
- `201` - Created
- `400` - Bad Request
- `401` - Unauthorized
- `403` - Forbidden
- `404` - Not Found
- `500` - Internal Server Error

## Security Features

- Password hashing with bcrypt
- JWT token expiration
- CORS configuration
- Input validation
- Role-based access control

## Development

### Project Structure
```
backend/
├── config/
│   └── database.js
├── middleware/
│   └── auth.js
├── models/
│   └── User.js
├── routes/
│   ├── auth.js
│   └── users.js
├── server.js
├── package.json
├── env.example
└── README.md
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

ISC 