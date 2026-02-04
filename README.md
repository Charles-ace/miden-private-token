# Miden Private Token

# 🛡️ Building a Private Token on Miden (Beginner Guide)

This repository documents my journey learning how to build privacy-preserving applications on **Polygon Miden**.

The goal is to build an encrypted token system step-by-step while learning Miden architecture.

---

## 📚 What Is Miden?

Miden is a zk-powered virtual machine that allows developers to build applications with:

- Private state
- Off-chain execution
- Zero-knowledge proofs
- Scalable smart contracts

Think of it as building smart contracts where users can keep balances and transactions private.

---

## 🎯 What You Will Learn

By following this series, you will learn:

- How Miden programs work
- How to set up Miden CLI
- How to create token logic
- How privacy works in zk systems
- How encrypted balances can be managed

---

## 🧰 Prerequisites

Before starting, you need:

- Linux / WSL / Mac terminal
- Rust installed
- Git installed
- Basic command line knowledge

---

## 📂 Project Structure

```
miden-private-token/
│
├── programs/        → Miden smart contract logic
├── scripts/         → Automation scripts
├── wallet/          → Account configuration
├── docs/            → Learning notes
└── README.md        → Guide
```

---

# 🚀 Day 1 — Environment Setup + Token Skeleton

---

## Step 1 — Install Rust

Run:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Verify:

```bash
rustc --version
```

---

## Step 2 — Install Miden CLI

```bash
cargo install miden-cli
```

Verify:

```bash
miden --help
```

---

## Step 3 — Create Project Folder

```bash
mkdir miden-private-token
cd miden-private-token
```

---

## Step 4 — Create Project Structure

```bash
mkdir programs
mkdir scripts
mkdir wallet
mkdir docs
```

---

## Step 5 — Create Token Issuer Program

Create file:

```bash
nano programs/issuer.mas
```

Paste:

```
begin
    push.1001
    push.100
    dup.1
end
```

Save and exit.

---

## Step 6 — Create Mint Script

```bash
nano scripts/mint.sh
```

Paste:

```bash
#!/bin/bash
miden run programs/issuer.mas
```

---

## Step 7 — Create Wallet Configuration

```bash
nano wallet/accounts.json
```

Paste:

```json
{
  "issuer": {
    "account_id": 1001
  }
}
```

---


You now have:

- Miden installed
- Project scaffold created
- Token issuer logic initialized
- Wallet configuration created
