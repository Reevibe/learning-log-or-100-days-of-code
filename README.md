# learning-log-or-100-days-of-code
### Day 1: Learned about Base Smart Contracts.
​Initialized Learning Log for Base Ecosystem. Today I officially started my journey into the Base ecosystem. I've set up this repository to track my progress and began researching the "Superchain" concept. Base is built on the OP Stack, which means it shares a lot of DNA with Optimism. My goal is to understand how L2s scale Ethereum while keeping fees low.
Day 2: Network Configuration 
Configure Base Sepolia RPC
​Log: Added the Base Sepolia Testnet to my wallet today. 
​Chain ID: 84532
​Currency: ETH
​Explorer: https://sepolia.basescan.org/
Also requested some testnet ETH from a faucet to prepare for contract deployments.
Day 3: Exploring BaseScan
docs: Day 3 - Learning to read L2 transactions
Log: Spent time on BaseScan today. It's interesting to see how "L1 Data Fees" and "L2 Execution Fees" are separated. Navigating the "Verified Contracts" section to see how other developers are structuring their code on Base.
Day 4: Foundry Installation
docs: Day 4 - Setup Foundry development environment
Log: Installed Foundry today. It’s a blazing-fast toolkit for Ethereum application development written in Rust. Ran forge init to see the default project structure. I prefer this over Hardhat because I can write my tests in Solidity instead of JavaScript.
Day 5: The Bridging Process
docs: Day 5 - Researching L1 to L2 bridging
​Log: Installed Foundry today. It’s a blazing-fast toolkit for Ethereum application development written in Rust. Ran forge init to see the default project structure. I prefer this over Hardhat because I can write my tests in Solidity instead of JavaScript.
Day 5: The Bridging Process
docs: Day 5 - Researching L1 to L2 bridging
Log: Documented the flow of assets. Moving ETH from Ethereum (L1) to Base (L2) involves a bridge contract. While deposits are fast (usually ~a few minutes), withdrawing back to L1 via the official bridge takes about 7 days due to the challenge period.
Day 6: L2 Fees vs L1 Fees
docs: Day 6 - Understanding the L1 Data Fee
Log: Learned why Base is so cheap today. On an L2, you pay an Execution Fee (the cost to run the code on Base) and an L1 Data Fee (the cost to post that data back to Ethereum). With the recent "Dencun" upgrade and EIP-4844, "Blobs" have made the L1 Data Fee significantly cheaper.
Day 7: Setting up Coinbase Wallet
docs: Day 7 - Integrated Coinbase Wallet for Dev
Log: Set up a dedicated developer wallet using Coinbase Wallet. It has great native support for Base and makes it easy to toggle between Mainnet and Sepolia Testnet. I’m focusing on the "Smart Wallet" features which allow for easier onboarding.
Day 8: Verified Contracts
docs: Day 8 - Analyzing Verified Contracts on BaseScan
​Log: Spent time reading through verified source code on BaseScan. I looked at a few popular NFT projects to see how they handle mint functions and how they optimize for gas by using ERC721A instead of the standard ERC721.
Day 9: Hardhat vs Foundry
docs: Day 9 - Comparing Dev Tooling
​Log: Doing a deep dive comparison. While Foundry is fast and uses Solidity for tests, Hardhat has a massive plugin ecosystem (like hardhat-deploy). For my next small contract, I’ll likely stick with Foundry for the speed.
Day 10: Week 2 Summary
docs: Day 10 - Milestone 1 Recap
Log: Two weeks in! I now have a solid grasp of how Base sits on top of Ethereum. My environment is fully configured, I have testnet funds, and I’ve analyzed several production-grade contracts. Next week, I’ll start documenting the actual code logic.
Day 11: Solidity Syntax Deep Dive
docs: Day 11 - Researching Solidity 0.8.x features
Log: Focused on Solidity 0.8.x updates today. The biggest change is the built-in overflow/underflow checking, which means we no longer need the SafeMath library. I’m also looking at the custom errors feature (error Unauthorized();), which is much more gas-efficient than using long strings in require statements.
Day 12: ERC-20 Token Logic
docs: Day 12 - Drafting ERC-20 implementation
​Log: Started drafting a basic fungible token (ERC-20). The core logic involves a mapping(address => uint256) to track balances and a transfer function. On Base, keeping these contracts lean is key to ensuring the L1 data fee stays as low as possible for users.
Day 13: OpenZeppelin Library Integration
docs: Day 13 - Adding OpenZeppelin standard imports
Log: Instead of writing every token function from scratch, I’m using OpenZeppelin’s audited libraries.
​import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
This ensures the contract follows the standard perfectly and includes security best practices like internal _mint logic.
Day 14: Deployment Script Basics
docs: Day 14 - Writing the deployment script logic
Log: Working on the script to actually push the contract to the chain. In Foundry, this means creating a Contract.s.sol script. I’m making sure to use vm.startBroadcast() so the transactions are actually signed and sent to the Base Sepolia testnet, not just simulated locally.
Day 15: Constructors vs. Initializers
docs: Day 15 - Learning about Upgradeable Contract patterns
Log: Interesting discovery today: if a contract is "Upgradeable," it cannot use a standard constructor. Instead, it uses an initialize function. This is because the Proxy contract doesn't see the logic contract's constructor. I'm documenting the Initializable pattern from OpenZeppelin to keep my options open for future upgrades.
