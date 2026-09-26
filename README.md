# 🔓 Week 3 Cybersecurity Internship: PDF Password Cracking & Hash Analysis

This repository contains the documentation, screenshots, and proof-of-concept (PoC) flags captured during Week 3 (Module 2) of my Cybersecurity Internship. 

The lab focuses on extracting hashes from password-protected PDF files, performing dictionary attacks using offline and online tools, and capturing CTF flags embedded within the unlocked documents.

---

## 🛠️ Lab Overview & Scope

* Module: Week 3 - Project Module 2: Password Cracking with Networkwalks Tools
* Instructor: [Insert Instructor Name]
* Company: [Insert Company Name / Networkwalks]
* Environment: Kali Linux (Oracle VirtualBox) & Windows Web Environment

---

## 🚀 Lab Objectives & Workflow

1. Hash Extraction: Extracting the $pdf$ hash format from encrypted PDF documents using CLI tools (pdf2john) and web-based extractors.
2. Dictionary Attacks: Running hash-matching attacks using wordlists (rockyou.txt) with John the Ripper.
3. Alternative Workflows: Utilizing web-based security utilities (OnlineHashCrack, Networkwalks Hash Calculator, and Networkwalks Password Cracker) to achieve the same operational objectives.
4. Flag Capture: Unlocking documents and verifying flags (nw{...}).

---

## 🔑 Demonstration & Results

### 1. Hash Extraction
* Tools Used: OnlineHashCrack / Networkwalks Hash Calculator
* Output Hash Example:
  ```text
  $pdf$4*4*128*-1060*1*16*55da15a5c14175da449753199e44971d32*32*777fd021a7f3c5ae598c0c6495c7f76e00000000000000000000000000000000*32*ceecdac74b19b5a62688d3b3524e1374c955cbb9cc3c45316494d9446ef81af1
  2. Password Cracking via John the Ripper (Kali Linux)
​Using the extracted hash files (hash1.txt, hash2.txt, hash3.txt) against the rockyou.txt dictionary:
# Decompress wordlist if necessary
sudo gzip -d /usr/share/wordlists/rockyou.txt.gz

# Run John the Ripper against the target hash
john --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt
Cracked Results Summary:
Target FileExtracted PasswordCaptured Flag
My-Locked-PDF1.pdfpassword1nw{networkwalks_flag1}
My-Locked-PDF2.pdfpassword1nw{networkwalks_persistence_jtr_270521}
My-Locked-PDF3.pdf1qaz2wsxnw{networkwalks_flag_260821_1}
3. Browser-Based Cracking (Networkwalks Tools)
​
Hash Extraction: Uploaded locked PDFs to networkwalks.com/hash-calculator to retrieve raw $pdf$ hash strings.
​Password Matching: Input hash strings into networkwalks.com/password-cracker using built-in dictionary lists to reveal cleartext passwords.
​




# 📌 Key Security Takeaways
​
Password Complexity: Simple dictionary words (e.g., password1, keyboard patterns like 1qaz2wsx) are highly vulnerable to basic wordlist attacks.
​Hash Storage: Encrypted files store hashes representing credentials; protecting or salted-hashing sensitive data is essential to prevent offline cracking.
​Best Practices: Use strong, multi-character passphrases combining uppercase, lowercase, numbers, and symbols to significantly increase crack time.
​

🙏 Acknowledgments
​Special thanks to my instructor Waqas Karim and networkwalks for providing hands-on lab environments and guided exercises.
​Disclaimer: All activities in this repository were conducted strictly for educational purposes within an authorized lab environment.
