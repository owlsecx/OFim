# 🦉 OFim

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OFim** — Host File Integrity Monitor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OFim — Host File Integrity Monitor. It provides baseline engine — walks chosen directories and records hash, size, mode, uid/gid, owner/group, mtime, ctime, inode, nlink, device, symlink target. Built-in demo/self-test paths and severity gates help validate detections without touching production when those flags are used.

---

## ✨ Features

- Baseline engine — walks chosen directories and records hash, size, mode, uid/gid, owner/group, mtime, ctime, inode, nlink, device, symlink target
- Hash algorithms — SHA-256, SHA-512, SHA3-256, BLAKE2b, BLAKE2s (streaming, size-capped)
- HMAC-SHA256 baseline signature with a private key stored in ~/OFim/hmac.key (0600) — tamper detection
- Compare engine — added / removed / modified / permission / ownership / type / inode / symlink retarget / metadata-only change classification
- Suspicious-change rules — new SUID/SGID, world- writable, /etc, /bin, /sbin, cron, systemd units, authorized_keys, sudoers, PAM, ld.so.preload, PATH binaries, hidden executables, kernel modules
- Severity model with configurable floor + --fail-on

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OFim                                     # interactive menu
./OFim demo
./OFim init -p /etc -p /bin
./OFim check --min-severity medium
./OFim --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
