### Fiat to USDC Conversion and Distribution System Documentation

This project lets users convert fiat (like USD) to USDC using a backend (Node.js & Express), frontend (React with Vite and Tailwind CSS), and smart contracts for blockchain interaction. The system includes a secure treasury wallet, transaction monitoring, and reconciliation to ensure reliable operations.

---
### Link To Github:https://github.com/Khushisrivastava9/charter-21BCE10091-task2

---
### Table of Contents
- **System Architecture**
- **Backend Setup**
- **Frontend Setup**
- **Smart Contract Setup**
- **Environment Variables**
- **Running the Project**
- **Folder Structure**
- **API Overview**

---

### System Architecture

1. **Backend (Node.js & Express):** Handles API requests, fiat-to-USDC conversions, and interacts with the smart contract.
2. **Frontend (React with Vite):** Interface where users can initiate conversions and view transaction history.
3. **Smart Contract (Solidity):** Ensures secure USDC transfers on the blockchain.
4. **Bank API (Fiat Onramp):** Detects fiat deposits and triggers USDC conversion.
5. **Transaction Monitoring:** Checks for transaction success and keeps records synced.
6. **Reconciliation System:** Matches fiat deposits with USDC transactions to catch any mismatches.

---

### Backend Setup

#### Prerequisites
- **Node.js** (v18+)
- **MongoDB** (local or cloud, e.g., MongoDB Atlas)
- **API** for fiat deposits

#### Steps
1. **Install Dependencies:**
   ```bash
   git clone https://github.com/your-repo/fiat-usdc-conversion.git
   cd fiat-usdc-conversion/backend
   npm install
   ```

2. **Environment Variables (.env):**
   ```
   PORT=5000
   MONGO_URI=your-mongo-uri
   FIAT_API_URL=your-fiat-api-url
   USDC_CONTRACT_ADDRESS=your-usdc-contract-address
   USDC_WALLET_PRIVATE_KEY=your-usdc-wallet-private-key
   ```

3. **Start the Backend:**
   ```bash
   npm run dev
   ```
   Backend runs at `http://localhost:5000`.

---

### Frontend Setup

#### Prerequisites
- **Node.js** (v18+)

#### Steps
1. **Install Dependencies:**
   ```bash
   git clone https://github.com/your-repo/fiat-usdc-conversion.git
   cd fiat-usdc-conversion/frontend
   npm install
   ```

2. **Environment Variables (.env):**
   ```
   VITE_API_BASE_URL=http://localhost:5000
   ```

3. **Start the Frontend:**
   ```bash
   npm run dev
   ```
   Frontend runs at `http://localhost:3000`.

---

### Smart Contract Setup

#### Prerequisites
- **Hardhat** (for Solidity contract deployment)
- **Ethereum Wallet** (like MetaMask)

#### Steps
1. **Install Dependencies:**
   ```bash
   cd smart-contract
   npm install
   ```

2. **Environment Variables (.env):**
   ```
   PRIVATE_KEY=your-private-key
   INFURA_API_KEY=your-infura-api-key
   ```

3. **Deploy Contract:**
   ```bash
   npx hardhat run scripts/deploy.js --network sepolia
   ```

---

### Folder Structure

**Backend:**
- `controllers/transactionController.js`: Handles transactions.
- `models/transactionModel.js`: Transaction schema.
- `routes/transactionRoutes.js`: Transaction API endpoints.

**Frontend:**
- `components/TransactionForm.jsx`: Form for user transactions.
- `components/TransactionList.jsx`: Shows transaction history.

---

### API Overview

1. **POST /transaction**
   - Starts fiat-to-USDC conversion.
   - **Request:**
     ```json
     { "fiatAmount": "100.00" }
     ```
   - **Response:**
     ```json
     { "status": "success", "transactionId": "12345" }
     ```

2. **GET /transactions**
   - Retrieves all transactions.
   - **Response:**
     ```json
     [ { "_id": "12345", "fiatAmount": "100.00", "status": "completed" } ]
     ```

--- 
