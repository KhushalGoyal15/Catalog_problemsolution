# 🔐 Shamir Secret Sharing (JS/TS)

This project is an implementation of Shamir's Secret Sharing algorithm in both JavaScript and TypeScript.

Shamir's Secret Sharing is a cryptographic algorithm that allows a secret (like a password or encryption key) to be split into parts. A minimum number of these parts (threshold) is required to reconstruct the original secret.

## 🧠 Problem Statement

The goal is to:
- Split a secret into N shares
- Require at least K shares to reconstruct the original secret
- Ensure that fewer than K shares give no information about the secret

## 🚀 How to Run

### Prerequisites
- Node.js (v14+ recommended)
- npm or yarn

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/shamir-secret-sharing.git
cd shamir-secret-sharing
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Run the JavaScript Version
```bash
node js/index.js
```

### 4. Run the TypeScript Version

If not compiled:
```bash
npx ts-node ts/index.ts
```

Or compile and run:
```bash
tsc ts/index.ts
node ts/index.js
```

## ⚙️ How It Works (In Short)

1. A random polynomial of degree k-1 is created, where the constant term is the secret
2. Each share is a point (x, y) on the polynomial
3. To reconstruct the secret, k or more shares are used to perform Lagrange Interpolation at x = 0 to recover the original secret

## 🛠️ Tech Stack

- JavaScript (Node.js)
- TypeScript
- Implemented from scratch (no external crypto libraries)


## 🔧 API Reference

### Main Functions

#### `splitSecret(secret, totalShares, threshold, prime?)`
Splits a secret into multiple shares.

**Parameters:**
- `secret` (number): The secret to be split
- `totalShares` (number): Total number of shares to generate
- `threshold` (number): Minimum number of shares needed to reconstruct the secret
- `prime` (number, optional): Prime number for finite field operations (default: 2^31 - 1)

**Returns:**
- Array of share objects: `[{x: number, y: number}, ...]`

**Example:**
```javascript
const shares = splitSecret(12345, 5, 3);
console.log(shares);
// Output: [{x: 1, y: 123456}, {x: 2, y: 234567}, ...]
```




