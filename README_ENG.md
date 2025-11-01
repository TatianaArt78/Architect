## 🚀 HelloArchitect — Smart Contract on Arc Testnet

This project demonstrates how to deploy a simple Solidity contract to the **Arc Testnet** using **Foundry** and **GitHub Actions**, without installing anything locally.

---

### 🧱 Contract

**File:** `src/HelloArchitect.sol`

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.30;

contract HelloArchitect {
    string private greeting = "Hello Architect!";

    event GreetingChanged(string newGreeting);

    function getGreeting() public view returns (string memory) {
        return greeting;
    }

    function setGreeting(string memory newGreeting) public {
        greeting = newGreeting;
        emit GreetingChanged(newGreeting);
    }
}

## 🌐 Deployment Details

✅ Successfully deployed to **Arc Testnet**

- **Deployer:** `0x8E3A079D4e48d8aC485c669367Ee6d60E4bF2dA6`  
- **Contract Address:** `0xF44789647F8FE0a27487b26eb92E4f3E1334487C`  
- **Transaction Hash:** [`0xfe4da8f10c5cb4e39c29772ae8c73a68068a303cb478d95f113039568f166efc`](https://explorer.arc.network/)

---

## ⚙️ Automated Deployment via GitHub Actions

**Workflow file:** `.github/workflows/deploy.yml`

Deployment is triggered manually from **Actions → Run workflow**.

**The job:**
- Installs Foundry  
- Compiles the contract  
- Deploys it to Arc testnet using your wallet’s private key and RPC URL stored in GitHub Secrets.

---

## 🧪 How to Reproduce

1. Create a new GitHub repo  
2. Add your Solidity file under `src/`  
3. Create two GitHub secrets:
   - `PRIVATE_KEY` → wallet private key (with test tokens)
   - `ARC_TESTNET_RPC_URL` → Arc testnet RPC endpoint  
4. Add a deploy workflow (`.github/workflows/deploy.yml`)  
5. Run it under **Actions** tab

---

## 📖 Resources

- 🌐 [Arc Docs – Deploy on Arc](https://docs.arc.network/arc/tutorials/deploy-on-arc)  
- 💧 [Arc Faucet](https://faucet.circle.com/)  
- 🔍 [Arc Explorer](https://testnet.arcscan.app/)

