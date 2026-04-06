# Bomba
BOMBA is a cryptographic system based on the principle of floating entropy. Unlike classical ciphers (AES, ChaCha20) where entropy is fixed (256 bits), BOMBA increases entropy linearly with message length.
-------------------------------------------------------------------------------------
You can plug your own generator, your own alphabet set, and your own number of measurements into BOMBA — in a sense, it's a **cryptographic constructor**. This demonstration used an LCG and omitted hmac, which reduces the actual cryptographic strength

Modifications:

BOMBA-SH - version with HMAC and CSPRNG ( SHA-256 ) ( bomba-csprng-hmac.html )

Z-BOMBA - floating Z measures, choose your Z ( z-bomba.html )

S-BOMBA - maximum speed, minimum parameters ( s-bomba.html )

--------------------------------------------------------------------

 BOMBA — The Punk Cipher (just kidding... or not?)

**BOMBA is pure DIY crypto**
---------------------------------------------------------------------
## Run via HTTPS Protocol

**Always run BOMBA over HTTPS.**

- The cipher uses `crypto.subtle` API (SHA-256, HMAC, etc.)
- These features are **only available in secure contexts** (HTTPS or localhost)
- Running over HTTP will cause runtime errors
---------------------------------------------------------------------------------
# BOMBA · Modification Policy

**When modifying the cipher, please preserve the original name at the beginning.** ( Like Bomba-X or Bomba-Treasure ). 

------------------------------------------------------

Bomba-Compression

Key Properties

✅ Deterministic — Same SEED always produces the same configurations

✅ Reversible — Configurations can be exactly restored from the SEED

✅ Scalable — Can pack any number of configurations into a fixed-size SEED

✅ Portable — 32-bit SEED is easy to store, transmit, or memorize

Why This MattersIn traditional cryptography, you store:

Keys (256 bits)

Configurations (1,280+ bits)

Parameters (variable)

With BOMBA compression, you store just one 32-bit SEED — and everything else is generated deterministically from it.

This is not compression. This is mathematical transformation of state space. 🔐
------------------------------------------------------------


 Architecture

The system is built on four levels:
Level	Component	Purpose
0	Super-Master SEED	Root key (any length string)
1	Platinum SEED (256 bits)	Two-factor transformation
2	Global Base (65k symbols)	Deterministic byte-to-symbol mapping
3	Z measurements (5-26)	Polymorphic encoding

Key advantage: Due to Z measurements, each byte can be represented by one of Z different symbols, making differential and linear cryptanalysis practically impossible.
---------------------------------------------------------------------------------
Core Transformations

XOR Transformation + Affine Transformation

Purpose: Ensures ciphertext depends on every key bit. Without XOR, known-plaintext attacks would be trivial. Affine Transmorfamtion for
obsfucation


---------------------------------------------------------------------------------
Two-Factor Protection

Platinum SEED = (Super-Master + Human Key)

    Factor 1: Super-Master SEED (can be stored)

    Factor 2: Human Key (entered each time)

Even if one factor is compromised, the other remains secret.

======================================================================================

Mathematical Proof ( by AI )

Entropy Formula:
math

S = H_{key} + L \times (M + \log_2(Z) \times B)

Where:

    H_{key} — Platinum SEED entropy (256 bits)

    L — message length

    M — mask bits (24 bits)

    Z — number of measurements

---------------------------------------------------

Language: JavaScript / TypeScript

Platforms: Browser, Node.js, React Native

License: MIT (Open Source)

Repository: github.com/koolkid90/bomba
--------------------------------------------------------------------------------------

P. S. (Post Scriptum)

Hello! The original idea of this cipher is mine, but I wrote it using vibe coding (coding with AI assistance). I've been studying cryptography for less than six months, but as far as I can tell — the encryption works.

I will be glad to receive tests and attacks on it, as well as modifications and improvements from the community.

This is an open invitation:

    Try to break it

    Suggest improvements

    Port it to other languages (Rust, C, Go, Python)

    Submit pull requests
------------------------------------------------------------------------------
Author: Pavel Bobkin  
Github: koolkid90

© 2026 BOMBA Cryptosystem. All rights reserved.

