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

OKafkaX is an offline Apache Kafka and ZooKeeper configuration auditor. It parses Java Properties, JAAS, and related unit/env files to review listeners, SASL, TLS, authorizers, ZooKeeper ACLs, and secret-at-rest posture. Findings include CWE and MITRE mapping with TXT/Markdown/JSON/CSV/SARIF export and CI severity gates.

---

## ✨ Features

- Faithful `java.util.Properties` parser with continuations, escapes, duplicate-key tracking, and file:line origin
- Role detection for ZooKeeper-mode broker, KRaft broker/controller, combined node, and ZooKeeper server
- Listener, SASL (PLAIN/OAUTHBEARER/JAAS), TLS, inter-broker, and controller channel review
- ZooKeeper auth providers, skipACL, 4lw whitelist, AdminServer, and quorum SASL/TLS checks
- Secret-at-rest and JVM option review (JMX remote without auth); offline `--root` discovery
- Export TXT / MD / JSON / CSV / SARIF; `--demo` self-test and `--fail-on` / `--min-severity` gates

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OKafkaX -c server.properties -z zoo.cfg --scan
./OKafkaX --root /opt/kafka --json -o kafka.json --fail-on high
./OKafkaX --demo --list-rules
./OKafkaX --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
