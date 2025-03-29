## Agora Blockchain - Frontend

## Table of Contents

- [Overview](#overview)
- [Tech Stack](#tech-stack)
- [Folder Structure](#folder-structure)
- [Setup & Installation](#setup--installation)
- [Contributing Guideline](#contributing-guideline)

---

## Overview

Agora's frontend is a decentralized voting platform built using Next.js to provide a transparent, secure, and user-friendly interface for electoral processes. The frontend interacts with smart contracts deployed on multiple blockchain networks, leveraging Chainlink CCIP for cross-chain functionality.

Key Features
🗳️ Decentralized Voting: Users can cast verifiable, tamper-proof votes.

🔗 Blockchain Integration: Utilizes Ethereum & other networks for secure election management.

🌍 Cross-Chain Support: Chainlink CCIP enables seamless interaction across different blockchains.

🔐 MetaMask Authentication: Users connect their wallets to participate in elections.

🚀 Optimized Performance: Built with Next.js, TailwindCSS, and Zustand for a responsive UI

---

## Tech Stack 🚀

- ![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)  
  **[Next.js](https://nextjs.org/):** A React framework for building the frontend.

- ![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)  
  **[Node.js](https://nodejs.org/en/):** A JavaScript runtime for server-side development.

- ![MetaMask](https://img.shields.io/badge/MetaMask-F6851B?style=for-the-badge)  
  **[MetaMask](https://metamask.io):** A browser extension for managing Ethereum accounts and blockchain interactions.

- ![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)  
  **[Vercel](https://vercel.com/):** A hosting platform for deploying the Next.js frontend with serverless functions.

- ![Wagmi](https://img.shields.io/badge/Wagmi-7289DA?style=for-the-badge&logo=wagmi&logoColor=white)  
  **[Wagmi](https://wagmi.sh/):** React hooks for seamless Ethereum contract integration.

- ![Tailwind CSS](https://img.shields.io/badge/TailwindCSS-38B2AC?style=for-the-badge&logo=tailwindcss&logoColor=white)  
  **[TailwindCSS](https://tailwindcss.com/):** A utility-first CSS framework for styling.

- ![Zustand](https://img.shields.io/badge/Zustand-ff9f1c?style=for-the-badge)  
  **[Zustand](https://zustand.docs.pmnd.rs/getting-started/introduction):** A minimal, fast state-management library for React.

---

## Folder Structure

```
client/
├── abi/                    # Stores contract ABIs (Application Binary Interface)
│   └── artifacts/          # Compiled contract artifacts
│       ├── CCIPSender.ts   # ABI for CCIP message sender contract
|       ├── Election.ts     # ABI for Election contract
│       └── ElectionFactory.ts  # ABI for Election factory contract
├── app/                    # Next.js application root
│   ├── components/         # Reusable React components
│   ├── create/             # Page for creating elections or candidates
│   ├── election/           # Election-related pages and logic
│   ├── helpers/            # Utility functions for frontend
│   ├── hooks/              # Custom React hooks for blockchain interactions
│   ├── profile/            # User profile-related pages
│   ├── constants.ts        # Contains app-wide constants (contract addresses, API keys, etc.)
│   ├── favicon.ico         # App favicon
│   ├── global.css          # Global styles for the application
│   ├── layout.tsx          # Layout component for the entire app
│   └── page.tsx            # Main entry page for the Next.js app
├── public/                 # Public assets (images, fonts, etc.)
├── .dockerignore           # Files and folders ignored by Docker
├── .env                    # Environment variables (API keys, RPC URLs, etc.)
├── .eslintrc.json          # ESLint configuration for code quality
├── .gitignore              # Files ignored by Git
├── Dockerfile              # Docker configuration for containerizing the app
├── package.json            # Project dependencies and scripts
├── postcss.config.mjs      # PostCSS configuration for styling
├── README.md               # Documentation about the project
├── tailwind.config.ts      # TailwindCSS configuration file
└── tsconfig.json           # TypeScript configuration

```

---

## Setup & Installation

1. **Navigate to the Client Directory**:

   ```bash
   cd client
   ```

2. **Install Dependencies**:

   ```bash
   npm install
   ```

3. **Run the Application**:

   ```bash
   npm run dev
   ```

4. **Create an `.env.local` file** with the following environment variables:

   ```bash
   NEXT_PUBLIC_SEPOLIA_RPC_URL=<your_sepolia_rpc_url>
   NEXT_PUBLIC_FUJI_RPC_URL=<your_fuji_rpc_url>
   NEXT_PUBLIC_AMOY_RPC_URL=<your_amoy_rpc_url>
   NEXT_PUBLIC_PINATA_JWT=<your_pinata_jwt>
   ```

5. **Visit the Live App at**:
   **[localhost](http://localhost:3000/)**

---

## Contributing Guideline

1. **Create an Issue**: For any feature requests, bugs, security concerns, or other issues, please create an issue in the repository and wait to be assigned before proceeding.
2. **Branch Management**: Always create a new branch on your forked repository to commit your changes.
3. **Pull Request Descriptions**: When submitting a pull request (PR), provide a detailed explanation in the description, outlining all changes and the reasons behind them.
4. **Community Engagement**: Post your issues and PR updates on the Agora-Blockchain [Discord channel](https://discord.gg/HrJ6eKJ28a) for visibility and discussion.

## Additional Points to Remember

1. **Testing and Code Quality**: Ensure all changes are thoroughly tested, and avoid introducing code smells.
2. **Small Changes**: If a frontend change involves fewer than 20 lines of code or if you are making documentation updates, you may directly create a PR without prior assignment.
3. **Assignment Requirement**: Do not submit unassigned PRs; they will be closed without review.
4. **Avoiding Overlap**: Before starting work, check existing issues and PRs to avoid duplicating efforts or conflicting changes.
5. **Open Review Period**: A new issue or PR will remain open for one week to allow other contributors to review and suggest improvements.
6. **Mentor Notification**: If your PR is left unattended for more than 1-2 weeks, depending on the contribution size, feel free to tag the mentors of Agora-Blockchain to get their attention.
7. **Completion Timeline**: An issue is expected to be completed within 5-30 days, depending on its complexity. If not completed within this timeframe, it may be reassigned to another contributor.
8. **Progress Updates**: If your work on an issue is taking longer than expected, ensure you provide regular updates in the issue’s or PR's comments to keep everyone informed.
9. **Working on Blockchain Components**:
   - **Error Interface Changes**: If modifying an interface for errors, ensure the corresponding error is added to `client/app/helper/ErrorMessage.ts`.
   - **Contract ABI Updates**: For changes to `ElectionFactory`, `Election`, or `CCIPSender` contracts, manually update the ABI files in `client/abi/artifacts/` (do not configure Hardhat to generate these paths automatically in the client directory).
