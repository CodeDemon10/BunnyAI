# ⚡ Web3 Deployment Dashboard

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![VS Code](https://img.shields.io/badge/VS%20Code-1.75+-blue.svg)
![Solidity](https://img.shields.io/badge/Solidity-0.8+-363636.svg)

**A full-featured Web3 smart contract deployment suite inside VS Code**

[Features](#-features) • [Installation](#-installation) • [Quick Start](#-quick-start) • [Documentation](#-documentation) • [Contributing](#-contributing)

</div>

---

## 🎯 Overview

Transform your VS Code into a **complete Web3 development environment**. Compile, deploy, test, and monitor smart contracts without ever leaving your editor. Think **Hardhat + Remix + Tenderly** — all integrated into VS Code.

### Why This Extension?

- 🚀 **Zero Context Switching** — Stay in your editor
- 🎨 **Beautiful Dashboard** — Clean, minimal UI with real-time updates
- ⚡ **Lightning Fast** — Deploy in seconds, not minutes
- 🔧 **Highly Configurable** — Works with any EVM-compatible chain
- 📊 **Smart Analytics** — Track gas, costs, and transaction history

---

## ✨ Features

### 🔨 **Smart Contract Compilation**
- ✅ One-click compilation using **Hardhat**
- ✅ Real-time compilation logs with syntax highlighting
- ✅ Error detection and line-by-line debugging
- ✅ Support for all Solidity versions (0.4.x - 0.8.x+)
- ✅ Automatic dependency resolution
- ✅ Compilation time tracking

### 🚀 **Multi-Chain Deployment**
- ✅ **Local Networks**: Hardhat Node, Ganache, Anvil
- ✅ **Testnets**: Sepolia, Goerli, Mumbai, Base Sepolia, Optimism Goerli
- ✅ **Mainnets**: Ethereum, Polygon, Arbitrum, Optimism, Base, BSC
- ✅ **L2s & Rollups**: zkSync, Scroll, Linea, Mantle
- ✅ Custom RPC endpoints with automatic chain ID detection
- ✅ Multi-signature wallet support

### 🎯 **Advanced Deployment Features**
- ✅ **Batch Deployment** — Deploy multiple contracts simultaneously
- ✅ **Constructor Arguments** — Interactive input for deployment parameters
- ✅ **Deployment Presets** — Save and reuse deployment configurations
- ✅ **Dry Run Mode** — Simulate deployments without spending gas
- ✅ **Deployment History** — Track all past deployments with timestamps
- ✅ **Auto-Verification** — Verify contracts on Etherscan/Polygonscan automatically

### 📊 **Real-Time Analytics Dashboard**
- ✅ **Gas Tracker** — Live gas price monitoring (Slow/Average/Fast)
- ✅ **Cost Estimator** — Calculate deployment costs before execution
- ✅ **Transaction Monitor** — Watch transactions in real-time with confirmations
- ✅ **Network Health** — Check RPC status and block height
- ✅ **Wallet Balance** — Display ETH/MATIC balance for deployment wallet
- ✅ **Gas History Charts** — Visualize gas trends over time

### 🔐 **Security & Configuration**
- ✅ **Encrypted Key Storage** — Secure private key management
- ✅ **Hardware Wallet Support** — Ledger & Trezor integration
- ✅ **Multi-Wallet Management** — Switch between wallets instantly
- ✅ **ENV File Integration** — Auto-load from `.env` files
- ✅ **Network Templates** — Pre-configured popular networks
- ✅ **Slippage Protection** — Prevent front-running on deployment

### 🧪 **Testing & Debugging**
- ✅ **Integrated Test Runner** — Run Hardhat tests from dashboard
- ✅ **Contract Interaction** — Call functions directly from UI
- ✅ **Event Listener** — Monitor contract events in real-time
- ✅ **Debug Mode** — Step-by-step transaction tracing
- ✅ **Mainnet Fork Testing** — Test against live blockchain state
- ✅ **Gas Profiling** — Identify expensive operations

### 📦 **Smart Features**
- ✅ **Auto-Save Deployments** — Contract addresses saved to JSON
- ✅ **ABI Export** — Automatic ABI extraction and formatting
- ✅ **Frontend Snippets** — Generate ethers.js/web3.js code
- ✅ **Contract Upgradeability** — UUPS and Transparent Proxy patterns
- ✅ **Multisig Factory** — Deploy Safe/Gnosis multisig contracts
- ✅ **NFT Metadata Helper** — IPFS upload integration

---

## 🛠️ Tech Stack

```
┌─────────────────────────────────────────────────┐
│           VS Code Extension Architecture         │
├─────────────────────────────────────────────────┤
│                                                  │
│  Frontend (Webview)                             │
│  ├── HTML + Tailwind CSS + Vanilla JS          │
│  ├── Real-time WebSocket for logs              │
│  └── Chart.js for analytics visualization       │
│                                                  │
│  Backend (Extension Host)                       │
│  ├── TypeScript (Node.js runtime)              │
│  ├── ethers.js v6 for blockchain interaction   │
│  ├── Hardhat CLI integration                    │
│  └── VS Code API for editor integration         │
│                                                  │
│  Data Layer                                      │
│  ├── JSON config files                          │
│  ├── SQLite for deployment history             │
│  └── Encrypted keystore for private keys        │
│                                                  │
└─────────────────────────────────────────────────┘
```

---

## 📂 Project Structure

```
web3-deployment-dashboard/
│
├── src/
│   ├── extension.ts              # Main extension entry point
│   ├── core/
│   │   ├── compiler.ts           # Hardhat compilation logic
│   │   ├── deployer.ts           # Multi-chain deployment engine
│   │   ├── gasTracker.ts         # Real-time gas price monitoring
│   │   └── verifier.ts           # Contract verification on explorers
│   │
│   ├── services/
│   │   ├── walletManager.ts      # Wallet & key management
│   │   ├── networkManager.ts     # Network configuration handler
│   │   ├── historyService.ts     # Deployment history tracker
│   │   └── analyticsService.ts   # Dashboard analytics
│   │
│   ├── ui/
│   │   ├── dashboardProvider.ts  # Webview provider
│   │   └── commands.ts           # VS Code command handlers
│   │
│   └── utils/
│       ├── logger.ts             # Custom logging utility
│       ├── encryption.ts         # Key encryption helpers
│       └── validators.ts         # Input validation
│
├── media/
│   ├── dashboard.html            # Main dashboard UI
│   ├── styles/
│   │   └── main.css              # Tailwind + custom styles
│   ├── scripts/
│   │   ├── dashboard.js          # Dashboard interactivity
│   │   ├── gasChart.js           # Gas price visualization
│   │   └── deployment.js         # Deployment flow handler
│   └── assets/
│       ├── logo.svg              # Extension logo
│       └── icons/                # Network icons
│
├── config/
│   ├── networks.json             # Pre-configured networks
│   ├── templates/                # Deployment templates
│   └── schemas/                  # JSON validation schemas
│
├── test/
│   ├── suite/                    # Integration tests
│   └── fixtures/                 # Test contracts
│
├── .vscode/
│   ├── launch.json               # Debug configurations
│   └── tasks.json                # Build tasks
│
├── package.json                  # Extension manifest
├── tsconfig.json                 # TypeScript config
├── README.md                     # This file
├── CHANGELOG.md                  # Version history
└── LICENSE                       # MIT License
```

---

## 🚀 Installation

### Method 1: VS Code Marketplace (Recommended)
1. Open VS Code
2. Press `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (Mac)
3. Search for "Web3 Deployment Dashboard"
4. Click **Install**

### Method 2: Manual Installation
```bash
# Download the .vsix file from releases
# In VS Code, press Ctrl+Shift+P and run:
Extensions: Install from VSIX...
```

### Method 3: Build from Source
```bash
git clone https://github.com/yourusername/web3-deployment-dashboard.git
cd web3-deployment-dashboard
npm install
npm run compile
code .
# Press F5 to launch Extension Development Host
```

---

## 🎬 Quick Start

### 1️⃣ Open Dashboard
```
Ctrl+Shift+P → "Web3: Open Deployment Dashboard"
```

### 2️⃣ Configure Network
```javascript
{
  "network": "sepolia",
  "rpc": "https://sepolia.infura.io/v3/YOUR_PROJECT_ID",
  "privateKey": "env:PRIVATE_KEY",  // Loads from .env
  "explorer": "https://sepolia.etherscan.io"
}
```

### 3️⃣ Compile & Deploy
1. Click **🔨 Compile** → Instant feedback with logs
2. Select contract from dropdown
3. Enter constructor arguments (if needed)
4. Click **🚀 Deploy** → Watch real-time progress
5. Get deployment details:
   - Contract Address: `0x1234...5678`
   - Transaction Hash: `0xabcd...ef01`
   - Gas Used: `2,345,678 (0.023 ETH)`
   - Block Explorer: [View on Etherscan ↗]

---

## 📖 Documentation

### Configuration File Schema
```json
{
  "networks": {
    "sepolia": {
      "rpc": "https://sepolia.infura.io/v3/...",
      "chainId": 11155111,
      "privateKey": "env:SEPOLIA_PRIVATE_KEY",
      "gasPrice": "auto",
      "explorer": "https://sepolia.etherscan.io"
    }
  },
  "contracts": {
    "MyToken": {
      "constructorArgs": ["TokenName", "TKN", 1000000],
      "verify": true,
      "gasLimit": 5000000
    }
  },
  "preferences": {
    "defaultNetwork": "sepolia",
    "autoVerify": true,
    "showGasEstimates": true
  }
}
```

### Available Commands

| Command | Shortcut | Description |
|---------|----------|-------------|
| `Web3: Open Dashboard` | `Ctrl+Shift+W` | Open main dashboard |
| `Web3: Compile Contracts` | `Ctrl+Shift+C` | Compile all contracts |
| `Web3: Deploy Contract` | `Ctrl+Shift+D` | Deploy selected contract |
| `Web3: View History` | — | Show deployment history |
| `Web3: Add Network` | — | Add custom network |
| `Web3: Switch Wallet` | — | Change active wallet |
| `Web3: Gas Tracker` | — | Open gas price monitor |

---

## 🎨 Screenshots

### Main Dashboard
```
╔══════════════════════════════════════════════════════════════╗
║  ⚡ Web3 Deployment Dashboard                                ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  Network: Sepolia (✓ Connected)         Gas: 25 gwei       ║
║  Balance: 0.5234 ETH                    Block: 8,234,567    ║
║                                                              ║
║  ┌────────────────────────────────────────────────────┐    ║
║  │ 🔨 Compile    🚀 Deploy    📊 Analytics    ⚙️ Config │    ║
║  └────────────────────────────────────────────────────┘    ║
║                                                              ║
║  📄 Contracts:                                              ║
║    ▸ MyToken.sol          [Compiled ✓]                     ║
║    ▸ MyNFT.sol            [Not Compiled]                   ║
║    ▸ Staking.sol          [Deployed ↗]                     ║
║                                                              ║
║  📈 Recent Deployments:                                     ║
║    • MyToken → 0x1234...5678 (2 mins ago)                  ║
║    • MyNFT   → 0xabcd...ef01 (1 hour ago)                  ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

---

## 🧩 Extension Settings

This extension contributes the following settings:

* `web3Dashboard.defaultNetwork`: Set default blockchain network
* `web3Dashboard.autoCompile`: Compile on file save
* `web3Dashboard.gasWarningThreshold`: Alert when gas > threshold (gwei)
* `web3Dashboard.showNotifications`: Show deployment notifications
* `web3Dashboard.theme`: Dashboard theme (light/dark/auto)
* `web3Dashboard.explorerApi`: Etherscan API key for verification

---

## 🚦 Roadmap

### ✅ v1.0 (Current)
- [x] Basic compilation & deployment
- [x] Multi-chain support
- [x] Gas tracking
- [x] Deployment history

### 🔄 v1.5 (In Progress)
- [ ] AI-powered contract analyzer
- [ ] Auto test case generator
- [ ] Contract upgrade assistant
- [ ] Integrated blockchain explorer

### 🔮 v2.0 (Planned)
- [ ] WalletConnect integration
- [ ] Multi-signature workflow
- [ ] CI/CD pipeline integration
- [ ] Team collaboration features
- [ ] Contract security scanner
- [ ] IPFS/Arweave integration

---

## 🤝 Contributing

We love contributions! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Development Setup
```bash
npm install
npm run watch    # Compile TypeScript in watch mode
npm run test     # Run test suite
npm run lint     # Check code style
```

---

## 📝 Changelog

See [CHANGELOG.md](CHANGELOG.md) for detailed version history.

---

## 📄 License

MIT License © 2025 [Your Name/Organization]

See [LICENSE](LICENSE) for full text.

---

## 🙏 Acknowledgments

- [Hardhat](https://hardhat.org/) - Smart contract development framework
- [ethers.js](https://docs.ethers.org/) - Ethereum library
- [VS Code Extension API](https://code.visualstudio.com/api) - Extension development
- [Tailwind CSS](https://tailwindcss.com/) - UI styling

---

## 💬 Support

- 📧 Email: support@web3dashboard.dev
- 💬 Discord: [Join our community](https://discord.gg/web3dashboard)
- 🐦 Twitter: [@web3dashboard](https://twitter.com/web3dashboard)
- 🐛 Issues: [GitHub Issues](https://github.com/yourusername/web3-deployment-dashboard/issues)

---

<div align="center">

**⭐ If you find this extension helpful, please star the repository!**

Made with ❤️ by the Web3 Developer Community

</div>
