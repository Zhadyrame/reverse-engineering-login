# reverse-engineering-login
# XOR Reverse Engineering (Fragmented Data Analysis)

## Overview
This project analyzes a compiled executable that generates multiple encrypted text fragments. The goal was to reconstruct the hidden message using reverse engineering techniques.

## Tools Used
- Ghidra
- Static analysis
- Python (manual decoding)

## Analysis
- The program generates 5 text files (part1–part5)
- Data is encrypted using XOR
- XOR key identified: 0x4B ('K')
- Fragment order discovered: [2, 0, 4, 1, 3]

## Decryption
Formula:
decrypted_byte = encrypted_byte ^ 0x4B

Example:
0x0c ^ 0x4B = 0x47 ('G')

## Reconstruction
Fragments were reordered and decrypted to form the final message:

Gratulationes vexillum

## Key Findings
- XOR encryption is weak and reversible
- Data fragmentation adds obfuscation
- Reverse engineering reveals hidden logic

## Conclusion
This lab demonstrates how static analysis can uncover hidden data and break simple encryption techniques.

## Disclaimer
This project is for educational purposes only.
