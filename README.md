# 🦉 OKafkaX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OKafkaX** — Apache Kafka / ZooKeeper Configuration Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

Offline Apache Kafka / ZooKeeper configuration auditor

---

## ✨ Features

- Faithful java.util.Properties parser (continuations, \uXXXX escapes, '=' / ':' / whitespace separators, duplicate-key tracking, per-key file:line origin)
- Role detection — ZooKeeper-mode broker, KRaft broker, KRaft controller, combined node, ZooKeeper server
- Listener model — listeners, advertised.listeners, listener.security.protocol.map, per-listener overrides
- Authorizer review — allow.everyone.if.no.acl.found, missing / deprecated / mode-mismatched authorizers, super.users wildcard & ANONYMOUS principals
- SASL review — PLAIN over cleartext, unsecured OAUTHBEARER, inline sasl.jaas.config secrets
- TLS review — ssl.client.auth, cipher suites, legacy protocols, hostname verification, keystore hygiene
- Inter-broker & KRaft controller channel encryption
- ZooKeeper server audit — auth providers, skipACL, 4lw whitelist, AdminServer, quorum SASL / TLS
- JAAS file parser — PlainLoginModule user_ stores, Kerberos keytabs, ZooKeeper super user, debug
- Secret-at-rest checks — keystore / truststore / key passwords in world-readable properties files
- JVM option review (systemd / env files) — JMX remote without authentication, JAAS file linkage
- Offline --root tree discovery, CWE + MITRE mapping
- Export TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Self-test --demo, CI gates --fail-on / --min-severity

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OKafkaX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
