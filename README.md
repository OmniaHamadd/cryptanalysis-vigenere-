# Breaking a Vigenère Cipher by Hand

A worked walkthrough of the classical cryptanalysis techniques I used in my MSc Ethical Hacking & Cryptography coursework: finding a Vigenère key length with **Kasiski examination** and the **Index of Coincidence**, then recovering the key with **chi-squared frequency analysis**. A final section reconstructs an **RSA private key from Shamir's Secret Sharing** shares using Lagrange interpolation.

> The ciphertext, key and numbers are a fresh example made for this article, not the coursework material. Built with AI assistance (Claude); I verified every calculation.

## Read it
[`Breaking_a_Vigenere_Cipher.pdf`](Breaking_a_Vigenere_Cipher.pdf) — 4 pages.

## Techniques covered
| Stage | Technique | What it does |
|---|---|---|
| Key length | Kasiski examination | Measures gaps between repeated ciphertext trigrams; the key length divides them |
| Key length | Index of Coincidence | Confirms the length by detecting where English letter frequencies reappear (≈0.0667) |
| Key recovery | Chi-squared analysis | Solves each key position as a Caesar cipher by matching English frequencies |
| RSA | Shamir's Secret Sharing | Recovers a threshold secret (the public exponent) via Lagrange interpolation over a finite field |
| RSA | Modular arithmetic | Derives the private key d = e⁻¹ mod φ(n) and decrypts |

## The honest bit
The naïve Kasiski approach (GCD of all trigram distances) fails on this text because of coincidental repeats, so the article shows how factor analysis plus the Index of Coincidence resolve it. Cross-validating with independent methods is the real lesson.
