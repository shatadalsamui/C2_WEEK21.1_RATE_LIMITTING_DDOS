# OTP Security Demonstration

## Understanding DDoS and Rate Limiting

### DDoS (Distributed Denial of Service)
A DDoS attack overwhelms a target server with a flood of internet traffic from multiple sources, making the service unavailable to legitimate users. It's like a traffic jam clogging up a highway, preventing regular traffic from reaching its destination.

### Rate Limiting
Rate limiting controls the number of requests a client can make to a server within a specific time frame. It's like a bouncer at a club, only allowing a certain number of people in per minute.

### Solutions at a Glance
1. **Rate Limiting**: Restrict requests per IP/user
2. **CAPTCHA**: Verify human users
3. **Web Application Firewall (WAF)**: Filter and monitor HTTP traffic
4. **Load Balancing**: Distribute traffic across multiple servers
5. **IP Blacklisting**: Block known malicious IPs

---

## Project Overview
This project demonstrates OTP (One-Time Password) security concepts, including rate limiting and brute force attack prevention. It consists of two main components:

1. **Backend Server**: A Node.js/Express server that implements OTP generation and validation with rate limiting.
2. **Attack Module**: A TypeScript application that demonstrates brute force attacks against the OTP system.

## Project Structure

```
.
├── backend/           # Backend server implementation
├── attack/           # Attack simulation scripts
└── README.md         # This file
```

## Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)
- TypeScript (installed globally or as dev dependency)

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd WEEK21.1_RATE_LIMITING_DDOS_CAPTCHAS
   ```

2. Install dependencies for both backend and attack modules:
   ```bash
   cd backend && npm install && cd ..
   cd attack && npm install && cd ..
   ```

## Usage

1. Start the backend server:
   ```bash
   cd backend
   npm run build
   npm start
   ```

2. In a separate terminal, run the attack simulation:
   ```bash
   cd attack
   npm run build
   npm start
   ```
## Security Considerations

This project is for educational purposes only. The attack module demonstrates how OTP systems can be vulnerable to brute force attacks if not properly secured.