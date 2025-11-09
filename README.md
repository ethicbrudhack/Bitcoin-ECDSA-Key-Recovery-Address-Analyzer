# 🧩 Bitcoin ECDSA Key Recovery & Address Analyzer

This project demonstrates an **automated ECDSA key recovery and address-matching analyzer** that:

- 📂 Loads Bitcoin addresses from a file  
- 🔐 Uses modular arithmetic and heuristic nonce exploration to reconstruct private keys  
- 💡 Converts recovered keys into valid Bitcoin addresses  
- 🧭 Compares them against known target or dataset addresses  
- 💾 Saves successful matches for auditing and research  

> ⚠️ **For cryptographic research and educational purposes only.**  
> This tool is designed to analyze and visualize the mathematics of ECDSA key derivation —  
> **not** to perform unauthorized private key recovery.

---

## ⚙️ Features

✅ Loads and parses address lists from `adresy.txt`  
✅ Decodes Bitcoin addresses to Hash160 format  
✅ Generates candidate ephemeral nonces `k` to test potential private keys  
✅ Converts private keys to Bitcoin addresses using **ECDSA (secp256k1)**  
✅ Compares generated addresses to target or known datasets  
✅ Logs matches automatically into `znalezionoBTCOLD.TXT`  
✅ Uses PCA and adaptive heuristics for learning-based search control  
✅ Modular, well-commented Python implementation  

---

## 📂 File Structure

| File | Description |
|------|-------------|
| `main.py` | Main recovery and analysis script |
| `adresy.txt` | Input file containing target Bitcoin addresses |
| `znalezionoBTCOLD.TXT` | Output file with successfully recovered addresses |
| `README.md` | Documentation (this file) |

---

## 🧠 How It Works

1️⃣ **Load Addresses**  
Reads valid Bitcoin addresses from `adresy.txt` and stores them in memory (supports legacy `1`, `3`, and `bc1` formats).

2️⃣ **Convert to Hash160**  
Each address is decoded via Base58Check to extract its 20-byte `hash160`.

3️⃣ **Generate Candidates**  
The script iteratively generates candidate private keys and computes:
r, s, z → k → d → address


4️⃣ **Compare Addresses**  
If a generated address matches one from the dataset or the target, it is written to:


znalezionoBTCOLD.TXT


5️⃣ **Verify and Save**  
The recovered key is logged with:


Private Key (HEX): <value>
Znaleziony adres: <address>


---

## ⚠️ Ethical Disclaimer

This tool is provided **for cryptographic research and security auditing only.**  
Do **not** use it for unauthorized wallet access or mainnet key recovery attempts.  

✅ Use cases:
- Analyzing weak RNG or nonce bias  
- Studying key recovery mathematics  
- Validating internal crypto libraries  

❌ Forbidden use:
- Extracting third-party keys  
- Attacking live blockchain systems  

---

## 🪪 License

MIT License  
© 2025 — Author: [ethicbrudhack]

BTC donation address: bc1q4nyq7kr4nwq6zw35pg0zl0k9jmdmtmadlfvqhr
