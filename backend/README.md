# Backend Server

This is the backend server that implements OTP generation and validation with rate limiting to prevent brute force attacks.

## Features

- OTP generation endpoint
- Password reset functionality
- Rate limiting for OTP requests (3 requests per 5 minutes)
- Rate limiting for password reset attempts (5 attempts per 15 minutes)
- In-memory OTP storage (for demonstration purposes)

## API Endpoints

### Generate OTP
```
POST /generate-otp
```
**Request Body:**
```json
{
    "email": "user@example.com"
}
```

**Response:**
```json
{
    "message": "OTP generated and logged"
}
```

### Reset Password
```
POST /reset-password
```
**Request Body:**
```json
{
    "email": "user@example.com",
    "otp": "123456",
    "newPassword": "newSecurePassword123"
}
```

**Success Response:**
```json
{
    "message": "Password has been reset successfully"
}
```

**Error Response:**
```json
{
    "message": "Invalid OTP"
}
```

## Rate Limiting

- **OTP Generation**: Limited to 3 requests per IP address every 5 minutes
- **Password Reset**: Limited to 5 attempts per IP address every 15 minutes

## Development

### Prerequisites
- Node.js (v14 or higher)
- npm (v6 or higher)

### Installation

1. Install dependencies:
   ```bash
   npm install
   ```

2. Build the TypeScript code:
   ```bash
   npm run build
   ```

3. Start the server:
   ```bash
   npm start
   ```

The server will start on `http://localhost:3000`

### Environment Variables

Create a `.env` file in the root directory with the following variables:

```
PORT=3000
NODE_ENV=development
```

## Security Notes

- This implementation uses in-memory storage for demonstration purposes only. In production, use a persistent database.
- For production use, consider implementing additional security measures such as:
  - IP-based blocking after multiple failed attempts
  - Account lockout after multiple failed attempts
  - More sophisticated rate limiting strategies