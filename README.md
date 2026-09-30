# 🔐 Multi-Target PDF Password Recovery Lab

![Domain](https://img.shields.io/badge/Domain-Cybersecurity%20%26%20Ethical%20Hacking-blue.svg)
![Tool](https://img.shields.io/badge/Tool-John%20the%20Ripper%20%7C%20Johnny%20GUI-orange.svg)
![Status](https://img.shields.io/badge/Flags-Captured%20(3%2F3)-brightgreen.svg)
![Environment](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)

A practical cybersecurity lab demonstrating offline cryptographic hash extraction, dictionary-based password recovery, and document decryption across multiple locked PDF targets using **John the Ripper** and **Johnny GUI**[cite: 1, 3, 4, 5, 6, 11].

---

## 🎯 Target Summary & Recovered Flags

| Target File | Extracted Hash File | Recovered Plaintext | Attack Type | Captured Flag |
| :--- | :--- | :--- | :--- | :--- |
| **`My Locked PDF1.pdf`** | `hash1.txt`[cite: 1, 7] | `password1` | Dictionary[cite: 1] | `Congratulations! You have captured your 1st flag.`[cite: 1] |
| **`My Locked PDF2.pdf`** | `hash2.txt`[cite: 7] | `good-luck` | Dictionary | `nw{networkwalks_persistence_jtr_270521}`[cite: 11] |
| **`My Locked PDF3.pdf`** | `hash3.txt`[cite: 7] | `1qaz2wsx` | Dictionary | `nw{networkwalks_flag_200021_1}`[cite: 6] |

---

## 🛠️ Tools Used
* **Operating System:** Windows 10/11 x64[cite: 1]
* **Target Files:** `My Locked PDF1.pdf`, `My Locked PDF2.pdf`, `My Locked PDF3.pdf`[cite: 1, 10]
* **Hash Parser:** Online Hash Crack (`onlinehashcrack.com`) via `pdf2john`[cite: 1, 9]
* **Cracking Engine:** John the Ripper (v1.9.0-jumbo-1 OMP x64)[cite: 1]
* **GUI Front-End:** Johnny GUI v2.2[cite: 1]
* **Viewer:** Google Drive PDF Viewer & Adobe Acrobat Reader[cite: 1, 6, 11]

---

## 🚀 Step-by-Step Execution

### Step 1: Verify Password-Protected Target
Target documents were inspected, confirming password encryption prompts blocking read access[cite: 1, 10].

![Step 1 - Locked PDF Prompt](screenshots/Screenshot%202026-09-30%20162926.png)

---

### Step 2: Upload Target Document for Hash Parsing
Uploaded the target PDF file to the online hash extraction tool to isolate the cryptographic signature[cite: 1, 9].

![Step 2 - Extractor Upload](screenshots/Screenshot%202026-09-30%20163003.png)

---

### Step 3: Extract the Cryptographic Hash Signature
The tool converted the document metadata into a standardized `$pdf$4*...` hash format[cite: 1, 8].

![Step 3 - Extracted Hash Output](screenshots/Screenshot%202026-09-30%20163016.png)

---

### Step 4: Save Hashes into the Workspace
Saved the isolated hash strings into separate text files (`hash1.txt`, `hash2.txt`, `hash3.txt`) ready for Johnny GUI ingestion[cite: 7].

![Step 4 - Local Hash Files Structure](screenshots/Screenshot%202026-09-30%20163034.png)

---

### Step 5: Crack Target 1 (`hash1.txt`)
Configured Johnny GUI to point to `john.exe`, imported `hash1.txt`, and ran **Start new attack**[cite: 1, 7].
* **Recovered Key:** `password1`[cite: 1, 3]

![Step 5 - Target 1 Cracked in Johnny](screenshots/Screenshot%202026-09-30%20163159.png)

---

### Step 6: Crack Target 2 (`hash2.txt`)
Imported `hash2.txt` into Johnny GUI and initiated the dictionary attack[cite: 7].
* **Recovered Key:** `good-luck`

![Step 6 - Target 2 Cracked in Johnny](screenshots/Screenshot%202026-09-30%20163147.png)

---

### Step 7: Crack Target 3 (`hash3.txt`)
Imported `hash3.txt` into Johnny GUI and recovered the keyboard walk pattern[cite: 5, 7].
* **Recovered Key:** `1qaz2wsx`

![Step 7 - Target 3 Cracked in Johnny](screenshots/Screenshot%202026-09-30%20163132.png)

---

### Step 8: Decrypt Target 2 & Retrieve Flag
Authenticated `My Locked PDF2.pdf` using `good-luck` to capture the hidden flag[cite: 4, 11].
* **Flag Captured:** `nw{networkwalks_persistence_jtr_270521}`[cite: 11]

![Step 8 - Flag 2 Decrypted](screenshots/Screenshot%202026-09-30%20162910.jpg)

---

### Step 9: Decrypt Target 3 & Retrieve Flag
Authenticated `My Locked PDF3.pdf` using `1qaz2wsx` to capture the hidden flag[cite: 5, 6].
* **Flag Captured:** `nw{networkwalks_flag_200021_1}`[cite: 6]

![Step 9 - Flag 3 Decrypted](screenshots/Screenshot%202026-09-30%20163119.jpg)

---
