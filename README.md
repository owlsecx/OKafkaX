# 🦉 OKafkaX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OKafkaX --help   # watch every network call
firejail --net=none ./OKafkaX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
