Solana Escrow
A smart contract (program) for the Solana blockchain that enables secure, trustless token exchanges between two parties using an escrow mechanism. This repository provides the core logic for initializing, exchanging, and canceling escrow transactions on Solana.

Table of Contents

#	Overview
#	Features
#	Environment Setup
#	Application Setup
#	Usage
#	Contributing
#	License
#	Acknowledgements

#Overview

This project implements an escrow program in Rust for the Solana blockchain. The escrow holds tokens from an initializer (party A) until a taker (party B) accepts the swap. Once both parties agree, the program executes the exchange and closes the temporary accounts. The design is inspired by established Solana escrow implementations and follows best practices for on-chain security.

## Workflow Diagram
![escrow_workflow_diagram](https://github.com/user-attachments/assets/27a91512-bbb1-49d6-beae-6fda27def9ca)


#Features

1.Initialize Escrow: Lock tokens in a temporary account pending a swap.

2.Exchange: Complete the swap when the taker accepts, atomically exchanging tokens.

3.Cancel: Allow the initializer to cancel and reclaim tokens if the swap is not accepted.

4.Secure: Uses Solana's program-derived addresses (PDAs) and SPL Token program for secure token management.



#Environment Setup

Before building or deploying, ensure your environment is ready:

1.Install Rust:https://www.rust-lang.org/tools/install

2.Install Solana CLI:https://docs.solana.com/cli/install-solana-cli-tools

3.Install Node.js and npm:https://nodejs.org/en/download/




#Additional Linux Dependencies

sudo apt-get install libssl-dev libudev-dev pkg-config zlib1g-dev llvm clang make


#Application Setup
Follow these steps to build and deploy the escrow program:

1.	Clone the repository:
git clone git@github.com:tothemoon023/Solana_Escrow.git
cd Solana_Escrow

2.Install npm dependencies:
npm install

3.	Build the smart contracts:
npm run build

4.	Check Solana CLI installation:
solana –version

5.	Configure Solana to use devnet:
solana config set --url https://devnet.solana.com

6.	Generate a new keypair:
solana-keygen new

7.	Request SOL from the devnet faucet:
solana airdrop 1

8.	Update configuration:
Edit solana.escrow.config.json to set the path to your keypair:
"keypairPath": "/path/to/your/id.json"

9.	Deploy the program:
npm run deploy



#Usage

Initialize an escrow:
Use the provided scripts or client code to create a new escrow, specifying the token accounts and amounts.
Accept and exchange:
The taker accepts the escrow, triggering the atomic swap.
Cancel escrow:
The initializer can cancel if the swap is not accepted, reclaiming their tokens.
Refer to the /tests folder for example scripts and usage patterns.



#Contributing

Contributions are welcome! To contribute:
Fork the repository
Create a new branch (git checkout -b feature/YourFeature)
Commit your changes (git commit -m 'Add feature')
Push to your branch (git push origin feature/YourFeature)
Open a Pull Request



#License

Distributed under the MIT License. See LICENSE for details.



#Acknowledgements

•	 Solana Docs
•	Rust Programming Language
•	TypeScript



