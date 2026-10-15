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

Host file integrity monitor with HMAC-signed baselines

---

## ✨ Features

- Baseline engine — walks chosen directories and records hash, size, mode, uid/gid, owner/group, mtime, ctime, inode, nlink, device, symlink target
- Hash algorithms — SHA-256, SHA-512, SHA3-256, BLAKE2b, BLAKE2s (streaming, size-capped)
- HMAC-SHA256 baseline signature with a private key stored in ~/OFim/hmac.key (0600) — tamper detection
- Compare engine — added / removed / modified / permission / ownership / type / inode / symlink retarget / metadata-only change classification
- Suspicious-change rules — new SUID/SGID, world- writable, /etc, /bin, /sbin, cron, systemd units, authorized_keys, sudoers, PAM, ld.so.preload, PATH binaries, hidden executables, kernel modules
- Severity model with configurable floor + --fail-on
- Change history journal (JSON-lines) + viewer
- Accept changes — re-baseline after review
- Exports — TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Exclude globs, max file size, one-filesystem mode
- Self-test demo — builds a sample tree, baselines, mutates and diffs it (fully sandboxed in a temp dir)
- Full CLI mode (init, check, paths, history, demo)

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OFim
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
