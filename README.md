# Base Horizon View (Built for Base)

Deployed on Base Mainnet.

Base Horizon View is a browser-first reference application designed for monitoring the Base blockchain, performing wallet connections, and reading real-time onchain data such as block details and address balances using Coinbase Wallet SDK and Base RPC endpoints.

---

## Base ecosystem alignment

Built for Base.

Supported networks:
- Base Mainnet  
  chainId (decimal): 8453  
  Explorer: https://basescan.org  

- Base Sepolia  
  chainId (decimal): 84532  
  Explorer: https://sepolia.basescan.org  

The application explicitly targets Base networks by chainId and relies on official Base RPC endpoints.

---

## What the script does

The app.base-horizon-view.ts script provides an in-browser interface that:

1) Connects a wallet using Coinbase Wallet SDK  
2) Reads and validates the active chainId  
3) Performs read-only Base RPC queries:
   - latest block number  
   - ETH balance of the connected address  
4) Fetches block stats (timestamp, gas usage)  
5) Allows ETH balance checks for arbitrary addresses  
6) Outputs Basescan links for verification  

All interactions are read-only. No transactions are broadcast.

---

## Repository structure

- app.base-horizon-view.ts  
  Browser-based script that connects to a wallet, toggles Base networks, and inspects onchain data.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - control.sol — contract demonstrating control structures like if-else conditions and custom error handling for time-based functions, including "FizzBuzz" logic and time-based responses 
  - structs.sol — contract for managing a garage of cars with struct-based data representation, including car details and custom error handling for invalid car indexes  

- package.json  
  Dependency manifest including Coinbase SDKs and multiple repositories from the Base GitHub organization.

- README.md  
  Technical documentation, Base references, licensing, and testnet deployment records.

---

## Libraries used

- @coinbase/wallet-sdk  
  Wallet connection layer compatible with Coinbase tooling and Base accounts.

- viem  
  RPC client used for Base reads and block inspection.

- Coinbase GitHub repositories  
  Included as dependencies to reference the broader Coinbase open-source ecosystem.

- Base GitHub repositories  
  Included as dependencies to document linkage with Base tooling and infrastructure.

---

## Installation and execution

Install dependencies using Node.js.  
Serve the project with a modern frontend dev server and open the page in a browser.

Expected result:
- Connected address printed with Basescan link  
- Active chainId displayed (8453 or 84532)  
- Read-only Base RPC data displayed  
- Block stats available on demand  

---

## License

MIT License

Copyright (c) 2025 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## Author

GitHub: https://github.com/anthill-aces  
Email: anthill_aces.0l@icloud.com   
Public contact: https://x.com/sebastienluf3 

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract "control" address:  
0xf329fc1de25492cd0abcea3b2eabc58d1472ee85

Deployment and verification:
- https://sepolia.basescan.org/address/0xf329fc1de25492cd0abcea3b2eabc58d1472ee85
- https://sepolia.basescan.org/0xf329fc1de25492cd0abcea3b2eabc58d1472ee85/0#code  

Contract "structs" address:  
0x8e0d6077d767c865c58b9b71e18be402292b9d28

Deployment and verification:
- https://sepolia.basescan.org/address/0x8e0d6077d767c865c58b9b71e18be402292b9d28
- https://sepolia.basescan.org/0x8e0d6077d767c865c58b9b71e18be402292b9d28/0#code  


These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
