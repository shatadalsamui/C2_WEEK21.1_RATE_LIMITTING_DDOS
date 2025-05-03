# OTP Brute Force Attack Simulation

This module demonstrates a brute force attack against an OTP (One-Time Password) system. It's designed for educational purposes to show the importance of proper security measures like rate limiting and account lockout policies.

## ⚠️ Important Notice

This tool is for **educational and security testing purposes only**. Only use it on systems you own or have explicit permission to test. Unauthorized testing against systems you don't own is illegal.

## Features

- Sequential OTP brute force attack
- Configurable batch processing
- Rate limiting to avoid detection
- Progress tracking and statistics
- Common OTP pattern testing

## Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)
- Target OTP server (by default: http://localhost:3000)

## Installation

1. Install dependencies:
   ```bash
   npm install
   ```

2. Build the TypeScript code:
   ```bash
   npm run build
   ```

## Usage

### Basic Usage

```bash
npm start
```

### Configuration

Edit the following variables in `src/index.ts` to customize the attack:

```typescript
const TARGET_EMAIL = "harkirat@gmail.com";  // Target email address
const TARGET_URL = "http://localhost:3000/reset-password";  // Target reset password endpoint
const NEW_PASSWORD = "hacked123";  // New password to set if attack is successful
const BATCH_SIZE = 50;  // Number of concurrent requests
const START_RANGE = 0;  // Starting OTP (0-999999)
const END_RANGE = 999999;  // Ending OTP (0-999999)
```

### Rate Limiting

The attack includes built-in rate limiting (3 requests per second by default) to avoid overwhelming the target server. You can adjust this in the code if needed.

## How It Works

1. The script first tries common OTP patterns (e.g., 123456, 111111, 000000, etc.)
2. If no match is found, it proceeds with a sequential brute force attack
3. OTPs are tested in batches for efficiency
4. Progress is displayed with the current OTP being tested and success rate

## Output Example

```
[+] Starting OTP brute force attack on test@example.com
[+] Target URL: http://localhost:3000/reset-password
[+] Starting at: 2023-10-15T12:00:00.000Z

[2023-10-15T12:00:01.234Z] Attempts: 1000 | OTP: 1999 | Rate: 15.67 req/s
[2023-10-15T12:00:31.567Z] Attempts: 2000 | OTP: 3999 | Rate: 16.23 req/s

[!] SUCCESS! Password has been reset!
[!] OTP: 123456
[!] New Password: hacked123
```