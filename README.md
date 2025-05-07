# PublicFund Transparency FundView

A full-stack DApp that allows users to make transparent donations to a smart contract on the Ethereum blockchain. Donations and spending transactions are recorded and viewable publicly. Includes QR code-based payments (e.g. via MetaMask mobile) and live ETH/USD/INR tracking.

---

## 🔧 Tech Stack

- **Frontend:** React(Nextjs) (QR-based donation UI)
- **Backend:** Express.js + Ethers.js
- **Smart Contract:** Solidity (Deployed on Sepolia testnet)
- **Blockchain:** Ethereum (via Sepolia testnet)
- **Web3 Tools:** MetaMask, Etherscan
- **Price API:** CoinGecko API

---

## ⚙️ Features

- 💰 **Donate via Smart Contract**
- 📜 **Transaction History** (Donations & Withdrawals)
- 📊 **Live ETH to USD/INR conversion**
- 📷 **QR Code Payment Support** (scan and donate with MetaMask mobile)
- 🧾 **Purpose Logging** (donation/spend with reason)
- 🛡️ **Basic Rate Limiting for API protection**

---

## 🚀 Getting Started

### 1. Clone the Repo

```bash
git clone https://github.com/yourusername/donation-tracker.git
cd donation-tracker


### 2. Install Dependencies

```bash
npm install
```

### 3. Create `.env` File

```env
PORT=3000
PRIVATE_KEY=your_wallet_private_key
SEPOLIA_RPC_URL=https://sepolia.infura.io/v3/YOUR_INFURA_KEY
CONTRACT_ADDRESS=0xYourDeployedContractAddress
```

> ⚠️ **Never expose your PRIVATE_KEY publicly. Use environment variables only.**

---

## 💻 Run the Server

```bash
node index.js
```

API will be running at: `http://localhost:3000`

---

## 📄 Smart Contract

### `DonationTracker.sol`

Key functions:

- `donate(string purpose)` – accepts ETH & logs transaction
- `spend(string purpose, uint amount)` – owner can withdraw funds
- `getTransactions()` – view all transactions
- `getContractBalance()` – returns contract's ETH balance

Deployed to Sepolia Testnet.

---

## 🔗 API Endpoints

| Route                 | Method | Description                          |
|----------------------|--------|--------------------------------------|
| `/`                  | GET    | Status check                         |
| `/balance`           | GET    | Get contract balance + USD/INR value |
| `/transactions`      | GET    | Fetch all transactions               |
| `/donor/:address`    | GET    | Get donations made by a user         |
| `/donate`            | POST   | Donate via backend (server wallet)   |
| `/withdraw`          | POST   | Owner withdraws with purpose         |

---

## 📱 QR-Based Donation (MetaMask Mobile)

1. User enters `amount` and `purpose` on frontend.
2. QR code is generated with deep link to MetaMask.
3. User scans QR and completes donation directly to contract.
4. Transactions are visible on `/transactions`.

---

## ✅ Example `.env`

```env
PORT=3000
PRIVATE_KEY=6ae8e5cbf73a1.................f72a
SEPOLIA_RPC_URL=https://sepolia.infura.io/v3/abc1234567890def
CONTRACT_ADDRESS=0xABC1234Def567890abcDEF1234567890abcdefAB
```

---

## 📸 Screenshot

![screenshot]()

---

## 📜 License

MIT

---

## 🙌 Author

Made with ❤️ by Team Vikasana

Feel free to contribute or fork the project.!
```