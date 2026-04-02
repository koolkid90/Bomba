# Bomba
BOMBA is a next-generation cryptographic system based on the principle of floating entropy. Unlike classical ciphers (AES, ChaCha20) where entropy is fixed (256 bits), BOMBA increases entropy linearly with message length.
-------------------------------------------------------------------------------------

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

XOR Transformation

const mask = (platinumSeed + position) & 0xFFFFFF;
const xored = plainByte ^ mask;

Purpose: Ensures ciphertext depends on every key bit. Without XOR, known-plaintext attacks would be trivial.


---------------------------------------------------------------------------------
Two-Factor Protection

Platinum SEED = (Super-Master + Human Key)

    Factor 1: Super-Master SEED (can be stored)

    Factor 2: Human Key (entered each time)

Even if one factor is compromised, the other remains secret.

======================================================================================

Language: JavaScript / TypeScript

Platforms: Browser, Node.js, React Native

License: MIT (Open Source)

Repository: github.com/koolkid90/bomba
--------------------------------------------------------------------------------------

Author: Pavel Bobkin  
Github: koolkid90

© 2026 BOMBA Cryptosystem. All rights reserved.

