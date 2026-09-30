# 🔐 Multi-Target PDF Password Recovery Lab

![Domain](https://img.shields.io/badge/Domain-Cybersecurity%20%26%20Ethical%20Hacking-blue.svg)
![Tool](https://img.shields.io/badge/Tool-John%20the%20Ripper%20%7C%20Johnny%20GUI-orange.svg)
![Status](https://img.shields.io/badge/Flags-Captured%20(3%2F3)-brightgreen.svg)
![Environment](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)

A practical cybersecurity lab demonstrating offline cryptographic hash extraction, dictionary-based password recovery, and document decryption across multiple locked PDF targets using **John the Ripper** and **Johnny GUI**.

---

## 🎯 Target Summary & Recovered Flags

| Target File | Extracted Hash File | Recovered Plaintext | Attack Type | Captured Flag |
| :--- | :--- | :--- | :--- | :--- |
| **`My Locked PDF1.pdf`** | `hash1.txt`| `good-luck` | Dictionary| `nw{cybersecurity_flag_captured_2608}` |
| **`My Locked PDF2.pdf`** | `hash2.txt` | `password1` | Dictionary | `nw{networkwalks_persistence_jtr_270521}` |
| **`My Locked PDF3.pdf`** | `hash3.txt` | `1qaz2wsx` | Dictionary | `nw{networkwalks_flag_200021_1}`|

---

## 🛠️ Tools Used
* **Operating System:** Windows 10/11 x64
* **Target Files:** `My Locked PDF1.pdf`, `My Locked PDF2.pdf`, `My Locked PDF3.pdf`
* **Hash Parser:** Online Hash Crack (`onlinehashcrack.com`) via `pdf2john`
* **Cracking Engine:** John the Ripper (v1.9.0-jumbo-1 OMP x64)
* **GUI Front-End:** Johnny GUI v2.2

---

## 🚀 Step-by-Step Execution

### Step 1: Verify Password-Protected Target
Target documents were inspected, confirming password encryption prompts blocking read access.

![Step 1 - Locked PDF Prompt](01_locked_pdf_prompt.png)

---

### Step 2: Upload Target Document for Hash Parsing
Uploaded the target PDF file to the online hash extraction tool to isolate the cryptographic signature.

![Step 2 - Extractor Upload](02_hash_extractor.png)

---

### Step 3: Extract the Cryptographic Hash Signature
The tool converted the document metadata into a standardized `$pdf$4*...` hash format.

![Step 3 - Extracted Hash Output](03_extracted_hash_output.png)

---

### Step 4: Save Hashes into the Workspace
Saved the isolated hash strings into separate text files (`hash1.txt`, `hash2.txt`, `hash3.txt`) ready for Johnny GUI ingestion.

![Step 4 - Local Hash Files Structure](04_local_hash_files.png)

---

### Step 5: Crack Target 1 (`hash1.txt`)
Configured Johnny GUI to point to `john.exe`, imported `hash1.txt`, and ran **Start new attack**.
* **Recovered Key:** `good-luck`

![Step 5 - Target 1 Cracked in Johnny](05_target1_cracked.png)

---

### Step 6: Crack Target 2 (`hash2.txt`)
Imported `hash2.txt` into Johnny GUI and initiated the dictionary attack.
* **Recovered Key:** `password1`

![Step 6 - Target 2 Cracked in Johnny](06_target2_cracked.png)

---

### Step 7: Crack Target 3 (`hash3.txt`)
Imported `hash3.txt` into Johnny GUI and recovered the keyboard walk pattern.
* **Recovered Key:** `1qaz2wsx`

![Step 7 - Target 3 Cracked in Johnny](07_target3_cracked.png)

---

