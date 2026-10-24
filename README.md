# IMSC1Forge Pro (v1.0.0)

> **W3C IMSC1 (TTML) Subtitle & Timed Text Studio, Cross-Format Converter & CLI Auditor**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](http://LICENSE) [![W3C Standard](https://img.shields.io/badge/Standard-W3C%20IMSC1%20%2F%20TTML-brightgreen.svg)](https://www.w3.org/TR/ttml-imsc1/) [![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/) ![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20CLI%20%7C%20Docker-purple.svg)

---

## 📽 Overview

**IMSC1Forge Pro** is an autonomous engineering workstation designed for localization studios, subtitlers, broadcast QC technicians, and VOD delivery teams. Built to eliminate costly QC rejections from streaming giants like Netflix, Disney+, Apple TV+, and Amazon Studios, it delivers:

1. **W3C IMSC1 / TTML Synthesis**: Generate production-ready XML timed text files with comprehensive `<styling>`, active `<layout>` regions, and precise paragraph cues (`<p>`).  
2. **Multi-Format Conversion**: Bidirectional conversions between SRT, WebVTT, and W3C IMSC1 Text Profiles.  
3. **Simulated Broadcast Monitor**: Interactive video player preview allowing visual inspection of subtitle positioning, line breaks, and readability against a simulated 16:9 UHD canvas.  
4. **10-Point Normative Auditor**: Automated verification engine validating XML schema conformance, BCP 47 language tags, media timebases, sequential timing, and character density bounds (\<80 chars/line).  
5. **Standalone Python CLI (`imsc-cli.py`)**: Scriptable, zero-dependency command-line utility for automated ingest pipelines.

---

## 🚀 Key Features

- **Strict W3C IMSC1 Conformance**: Declares official namespaces (`http://www.w3.org/ns/ttml`, `ittp`, `ittm`) and profile designation URI (`http://www.w3.org/ns/ttml/profile/imsc1/text`).  
- **Clock & Frame Timebase Precision**: Seamlessly switch between clock-time (`HH:MM:SS.mmm`) and frame-time (`HH:MM:SS:FF`) expressions at 24, 25, 29.97, and 23.976 fps.  
- **Broadcast Readability Protection**: Checks character density and detects timing anomalies (negative intervals or overlapping cues).  
- **SMPTE IMF & Streaming Ready**: Produces XML streams ready to be multiplexed into SMPTE ST 2067-2 IMF packages or transcoded into WebVTT for HLS/DASH streaming.  
- **Zero Heavy Dependencies**: Pure standard library Python 3 CLI and modern HTML5/ES6 web studio.

---

## 🛠 Quick Start

### 1\. Interactive Web Studio

Open `source-code/index.html` directly in any modern web browser:

- Paste SRT cues into the Input Editor.  
- Configure stream metadata (Language, Title, Frame Rate).  
- Click **"Synthesize IMSC1 XML"** to view and copy standard XML.  
- Check the **Broadcast Video Preview** to inspect subtitle overlays.  
- Export to **WebVTT** or **SRT**.  
- Run the **10-Point Normative Auditor**.

### 2\. Standalone Python CLI

\# Display CLI help

python3 build/imsc-cli.py \--help

\# Convert an SRT file to W3C IMSC1 (TTML)

python3 build/imsc-cli.py convert subtitles.srt \--out subtitles.ttml \--lang en \--fps 24

\# Audit an existing IMSC1/TTML file

python3 build/imsc-cli.py audit subtitles.ttml

\# Convert SRT to WebVTT

python3 build/imsc-cli.py vtt subtitles.srt \--out subtitles.vtt

### 3\. Run Automated Test Suite

python3 test\_imsc.py

---

## 📁 Repository Structure

product\_276/

├── README.md                          \# Main project overview & user manual

├── test\_imsc.py                       \# 10-point automated unit test suite

├── source-code/

│   ├── index.html                     \# Interactive multi-tab Studio UI

│   ├── imsc.css                       \# Broadcast dark theme stylesheet

│   ├── imsc-engine.js                 \# IMSC1 / TTML synthesis and parsing engine

│   ├── imsc-auditor.js                \# 10-point normative compliance rules

│   └── app.js                         \# Application event controller & UI glue

├── build/

│   ├── imsc-cli.py                    \# Standalone executable CLI utility

│   └── imsc1forge-pro-v1.0.0.zip      \# Complete production release package

├── documentation/

│   ├── ARCHITECTURE.md                \# W3C IMSC1 specification deep-dive

│   ├── USER\_GUIDE.md                  \# Comprehensive operational manual

│   └── MONETIZATION\_AND\_MARKETING\_PLAYBOOK.md \# Commercial strategy & pricing tiers

└── screenshots/

    └── imsc-studio-preview.svg        \# High-resolution vector preview of GUI

---

## 📄 License

Released under the MIT License. Copyright © 2026 Autonomous Digital Product Factory.