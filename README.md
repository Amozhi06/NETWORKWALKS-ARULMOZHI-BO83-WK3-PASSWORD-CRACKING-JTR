# NETWORKWALKS-ARULMOZHI-BO83-WK3-PASSWORD-CRACKING-JTR
Security analysis lab: Extracting $pdf$ hashes and conducting dictionary attacks using John the Ripper (JTR Jumbo) across multiple encrypted targets.
# 🔐 Multi-Target PDF Password Recovery & Hash Auditing Lab

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
| **`My Locked PDF1.pdf`** | `hash1.txt` | `password1` | Dictionary | `Congratulations! You have captured your 1st flag.` |
| **`My Locked PDF2.pdf`**[cite: 10] | `hash2.txt` | `good-luck` | Dictionary | `nw{networkwalks_persistence_jtr_270521}` |
| **`My Locked PDF3.pdf`**[cite: 9, 10] | `hash3.txt` | `1qaz2wsx` | Dictionary | `nw{networkwalks_flag_200021_1}` |

---

## 🛠️️ Lab Tools & Setup

* **Host System:** Windows 10/11 x64
* **Target Files:** `My Locked PDF1.pdf`, `My Locked PDF2.pdf`, `My Locked PDF3.pdf`[cite: 1, 10]
* **Hash Extraction:** Online Hash Crack (`onlinehashcrack.com`) utilizing `pdf2john` algorithms[cite: 1, 9]
* **Cracking Suite:** John the Ripper (JTR v1.9.0-jumbo-1 OMP x64)[cite: 1]
* **GUI Front-End:** Johnny GUI v2.2[cite: 1]
* **Validation Environment:** Google Drive PDF Viewer & Adobe Acrobat Reader[cite: 1, 6, 11]

---

## 🔬 Step-by-Step Methodology & Execution

### 1. Hash Extraction (`pdf2john` Format)
Each locked PDF file was uploaded to the hash extraction portal to extract its crackable signature[cite: 1, 9]. The extracted strings (starting with `$pdf$4*...`) were saved into individual text files inside the project working directory[cite: 1, 7, 8]:
* `hash1.txt` -> Hash for `My Locked PDF1.pdf`
* `hash2.txt` -> Hash for `My Locked PDF2.pdf`[cite: 7]
* `hash3.txt` -> Hash for `My Locked PDF3.pdf`[cite: 7, 9]

