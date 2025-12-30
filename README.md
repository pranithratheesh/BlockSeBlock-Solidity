1️⃣ Donation Smart Contract

A simple contract that allows users to donate Ether and enables the owner to withdraw funds securely.

Features

Accepts Ether donations

Tracks total donations per address

Owner-only withdrawal functionality

Emits events for donations and withdrawals

Provides contract balance check

Concepts Used

mapping

payable functions

modifier

events

Owner-based access control

2️⃣ Library (Book Borrowing) Smart Contract

A library system where users can borrow a book by paying a fixed fee and are penalized for late returns.

Rules

Fixed borrow fee

Borrow duration: 1 day

Late return penalty: 0.0001 ETH per day

Penalty increases with each day of delay

Librarian (contract owner) controls withdrawals

Features

Tracks borrowing time per user

Calculates late penalties using block.timestamp

Enforces exact fee and penalty payments

Emits events for borrow and return actions

Concepts Used

struct

mapping

Time units (days)

block.timestamp

Payable functions

Events and modifiers

🛠️ Tech Stack

Solidity: ^0.8.2

IDE: Remix Ethereum

Blockchain: Ethereum (local / testnet)

🚀 How to Use

Open Remix IDE

Copy any contract from this repository

Compile using Solidity 0.8.x

Deploy

Interact using the Deploy & Run Transactions panel

Send ETH using the Value field (select ether unit)

🎯 Purpose

This repository is meant for:

Learning Solidity fundamentals

Understanding real-world smart contract logic

Practicing Ethereum development

Interview preparation and hands-on experimentation

📌 Notes

Events are used for logging and transparency

ETH transfers use call instead of deprecated transfer

Time units are internally stored in seconds

📄 License

GPL-3.0
