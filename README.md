# Blockchain Mini-Ledger

An advanced, lightweight Python implementation of a distributed ledger system built from scratch. This project demystifies core blockchain fundamentals—including cryptographic hashing, block architecture, mathematical consensus (Proof-of-Work), and immutable chain integrity verification—without relying on external cryptocurrency frameworks.

---

## 🚀 Core Mechanics & Architecture

### 🧱 1. Block Data Structure
Each block in the ledger is modeled as an immutable cryptographic object containing the following attributes:
* `index`: A unique, incremental identifier indicating the block's position in the chain.
* `timestamp`: A precise record of when the block was successfully mined.
* `data`: The transactional payload stored within the block.
* `previous_hash`: The cryptographic fingerprint of the preceding block, creating an un-breakable link.
* `nonce`: An arbitrary integer mutated continuously during the mining process to satisfy consensus difficulty.

### 🔐 2. Cryptographic Hashing & Proof-of-Work (PoW)
* **SHA-256 Security:** Utilizes Python's native `hashlib` to generate deterministic, fixed-size hashes based on serialized JSON block headers.
* **Consensus Mining:** Features a customizable Proof-of-Work function that forces the system to locate a valid `nonce` value such that the block's resulting hash begins with a strict target difficulty of $N$ leading zeros.

### 🛡️ 3. Dynamic Chain Validation & Tamper Simulation
* **Integrity Auditing:** Includes an automated validation loop that scans the entire ledger sequentially to ensure that no historical block hashes have been modified and that every `previous_hash` accurately points to its absolute ancestor.
* **Attack Demonstration:** Features an explicit test suite simulating an adversarial data modification attack on a historical block, demonstrating how a single-character mutation breaks downstream cryptographic integrity and invalidates the entire chain.

---

## 🛠️ Tech Stack & Prerequisites

* **Language:** Python 3.8+
* **Standard Libraries:** `hashlib`, `json`, `time`, `datetime`
* **Paradigm:** Object-Oriented Programming (OOP)

---

## 📂 System Flow Simulation

1. **Genesis Initialization:** The chain generates an immutable Block 0 (`Genesis Block`) with a hardcoded previous hash.
2. **Transaction Entry:** User-defined ledger data is staged for the upcoming block.
3. **Mining Loop:** The CPU computes millions of SHA-256 variations per second adjusting the `nonce` until the network's difficulty constraints are satisfied.
4. **Validation Routine:** The system audits the block links, visualizing the structural stability or highlighting the specific point of failure if a tampering vector is detected.

---
