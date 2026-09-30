# 🔐 Multi-Target PDF Password Cracking & Hash Analysis Lab

![Domain](https://img.shields.io/badge/Domain-Cybersecurity%20%26%20Ethical%20Hacking-blue.svg)
![Tool](https://img.shields.io/badge/Tool-John%20the%20Ripper%20%7C%20Johnny%20GUI-orange.svg)
![Status](https://img.shields.io/badge/Flags-Captured%20(3%2F3)-brightgreen.svg)
![Environment](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)

---

## 📌 Executive Summary

Password-protected PDF files do not store plaintext credentials directly; instead, they embed encrypted document keys alongside cryptographic hash digests used to verify input passwords[cite: 1, 2]. 

In this lab, I conducted an offline cryptanalytic audit against three password-locked target documents (**`My Locked PDF1.pdf`**, **`My Locked PDF2.pdf`**, and **`My Locked PDF3.pdf`**)[cite: 1, 10]. By isolating each document's `$pdf$` hash structure using online extraction utilities and running dictionary attacks through **John the Ripper (JTR Jumbo)** via the **Johnny GUI**, all three passwords were recovered, the documents unlocked, and the corresponding competition flags retrieved[cite: 1, 3, 4, 5, 6, 11].

---

## 🎯 Target Summary & Recovered Flags

| Target File | Extracted Hash File | Recovered Password | Attack Type | Captured Flag |
| :--- | :--- | :--- | :--- | :--- |
| **`My Locked PDF1.pdf`** | `hash1.txt` | `password1` | Dictionary| `Congratulations! You have captured your 1st flag.`|
| **`My Locked PDF2.pdf`**| `hash2.txt` | `good-luck` | Dictionary | `nw{networkwalks_persistence_jtr_270521}` |
| **`My Locked PDF3.pdf`**| `hash3.txt` | `1qaz2wsx` | Dictionary | `nw{networkwalks_flag_200021_1}` |

---

## 🛠 Lab Tools & Setup

* **Host System:** Windows 10/11 x64[cite: 1]
* **Target Files:** `My Locked PDF1.pdf`, `My Locked PDF2.pdf`, `My Locked PDF3.pdf`[cite: 1, 10]
* **Hash Extraction:** Online Hash Crack (`onlinehashcrack.com`) utilizing `pdf2john` algorithms[cite: 1, 9]
* **Cracking Suite:** John the Ripper (JTR v1.9.0-jumbo-1 OMP x64)[cite: 1]
* **GUI Front-End:** Johnny GUI v2.2[cite: 1]
* **Validation Environment:** Google Drive PDF Viewer & Adobe Acrobat Reader[cite: 1, 6, 11]

---

## 🔬 Step-by-Step Methodology & Evidence

### Step 1: Target Identification & Lock Verification
The target files were inspected, confirming standard password encryption prompts preventing document access[cite: 1, 10].

> **Action:** Opened `My Locked PDF3.pdf` requiring an authentication key[cite: 10].

![Step 1 - Locked PDF Prompt](screenshots/Screenshot%202026-09-30%20162926.png)

---

### Step 2: Uploading Target to Hash Extractor
To conduct an offline attack, the cryptographic hash must be isolated from the PDF metadata using `pdf2john` parsing logic[cite: 1, 9].

> **Action:** Uploaded `My Locked PDF3.pdf` to the Online Hash Crack extractor interface[cite: 9].

![Step 2 - Uploading to Hash Extractor](screenshots/Screenshot%202026-09-30%20163003.png)

---

### Step 3: Extracting the Cryptographic Hash
The extraction engine parsed the document parameters and produced the raw hash digest starting with `$pdf$4*...`[cite: 1, 8].

> **Action:** Copied the complete hash output for offline auditing[cite: 1, 8].

```text
$pdf$4*4*128*-1028*1*16*34eb542eff4e1b0b32d25ce15a9a7281*32*b77872bfc9a24fb2f845066283a8fc1b0021446990b9e4114071a4d9104984c1*32*e7572256e4b552cd57988f5134214b91920d94d7a6bf550ea94a2995c7f2ab02
