---
Title: Scalable translation validation of unverified legacy OS code
---

Describes a toolchain for translation validation of radere2 reverse engineering tool using Arm's ASL specification based on the PVS7 theorem prover.

Uses multiple techniques to validate translation of ASL to PVS7.
Tested using 370 functions extracted from Linux and Google's Zircon OS.
Limited to loop-free leaf functions.