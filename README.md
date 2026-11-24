# Evidentix Local AI

<p align="center">
  <img src="https://raw.githubusercontent.com/csibmohsin/Evidentix-Local-AI/main/screenshots/chatbox.jpeg" alt="Evidentix Local AI Interface" width="280" />
</p>

<p align="center">
  <b>Enterprise-Grade, Privacy-Centric On-Device Language Model Execution for Android</b><br />
  <i>Complete Data Sovereignty • Zero Cloud Latency • Hardware-Optimized Native Runtime</i>
</p>

<p align="center">
  <a href="https://github.com/csibmohsin/Evidentix-Local-AI/releases/download/v1.0.0/Evidentix-AI.apk">
    <img src="https://img.shields.io/badge/Download_Binary-Evidentix--AI.apk-0366d6?style=flat-square&logo=android&logoColor=white" alt="Download APK" />
  </a>
  <img src="https://img.shields.io/badge/Platform-Android_8.0%2B-informational?style=flat-square" />
  <img src="https://img.shields.io/badge/Architecture-ARM64--v8a_%7C_x86__64-informational?style=flat-square" />
  <img src="https://img.shields.io/badge/Model_Format-GGUF-informational?style=flat-square" />
  <img src="https://img.shields.io/badge/Network-Air--Gapped_100%25_Offline-success?style=flat-square" />
</p>

---

## Executive Summary

Evidentix Local AI is a production-ready mobile platform engineered to execute quantized Large Language Models (LLMs) locally on Android devices without external network connectivity. By utilizing high-efficiency C++ native bindings powered by `llama.cpp` and hardware-specific CPU/GPU instructions, Evidentix delivers low-latency, deterministic text generation while guaranteeing absolute data privacy.

All prompt processing, contextual memory allocation, and token generation occur strictly within the client device sandbox.

---

## Release Artifacts

| Parameter | Value |
| :--- | :--- |
| **Package Name** | `in.csib.evidentix.localai` |
| **Artifact** | `Evidentix-AI.apk` |
| **Release Version** | `1.0.0` |
| **File Size** | 34.38 MB (36,051,729 bytes) |
| **SHA-256 Checksum** | `B5A5CF9AFD5CB280AF3DC5327D052A6513F38CEABC6CCFC8E0E545D5F349EA9E` |
| **Direct Download** | [Download Evidentix-AI.apk](https://github.com/csibmohsin/Evidentix-Local-AI/releases/download/v1.0.0/Evidentix-AI.apk) |

---

## Architectural Comparison

| Dimension | Evidentix Local AI | Conventional Cloud AI (API-Based) |
| :--- | :--- | :--- |
| **Inference Location** | On-Device (SoC CPU/GPU) | Remote Data Center Servers |
| **Data Transmission** | Zero bytes transmitted externally | Continuous payload transfer |
| **Internet Dependency** | Completely autonomous / Air-gapped | Mandatory high-bandwidth connection |
| **Operational Privacy** | Complete client-side isolation | Subject to third-party data retention policies |
| **Recurring Usage Cost** | Zero (No subscription or API billing) | Token-based consumption billing |
| **Account Requirement** | None (Immediate initialization) | Mandatory authentication & telemetry |

---

## Core Capabilities

### 1. Zero-Configuration Deployment
The application requires no developer tools, virtualization layers, or command-line configurations. Deployment is achieved via standard Android package installation, presenting a modern interface ready for immediate execution.

### 2. Multi-Model GGUF Architecture
The runtime provides comprehensive compatibility with open-weights models formatted in GGUF:
- Native execution support for leading architectures including Qwen, SmolLM, and Llama families.
- On-the-fly model switching with deterministic context deallocation to eliminate memory leaks.

### 3. Integrated Model Download Center
Users can acquire verified, pre-quantized models directly through an in-app repository interface featuring:
- Direct streaming from high-availability mirrors.
- Checksum validation and error recovery during packet loss.
- Background transfer management with real-time throughput metrics.

### 4. Flexible Storage Ingestion
In addition to the download catalog, the system supports custom offline model loading:
- Local filesystem access via the Android Storage Access Framework (SAF).
- Direct ingestion from external mass storage (USB OTG / NVMe drives) utilizing zero-copy buffered streaming to prevent memory pressure.

### 5. Real-Time Hardware Telemetry
A dedicated monitoring subsystem tracks hardware parameters dynamically:
- Memory footprint inspection: Active process RAM, available headroom, and Out-Of-Memory thresholds.
- Inference performance tracking: Generation speed calculated in real-time (tokens per second).

### 6. Isolated Local Persistence
Conversational sessions and user configurations are persisted within an encrypted SQLite/Room database located strictly inside the app private directory.

---

## Interface Overview

| Model Selection & Telemetry | Integrated Download Center | Local Inference Chatbox |
| :---: | :---: | :---: |
| <img src="https://raw.githubusercontent.com/csibmohsin/Evidentix-Local-AI/main/screenshots/model-selection.jpeg" width="240" /> | <img src="https://raw.githubusercontent.com/csibmohsin/Evidentix-Local-AI/main/screenshots/model-download.jpeg" width="240" /> | <img src="https://raw.githubusercontent.com/csibmohsin/Evidentix-Local-AI/main/screenshots/chatbox.jpeg" width="240" /> |
| Real-time memory telemetry and dynamic model swapping | One-click downloads with live byte progress | Low-latency on-device response streaming |

---

## Verified Model Specifications

The built-in catalog provides validated configurations optimized for mobile SoCs:

| Model Name | Parameters | Quantization | Approximate Size | Minimum System RAM | Recommended Use Profile |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **SmolLM2 Instruct** | 360M | Q4_K_M | ~229 MB | 3 GB | Ultra-low latency responses, entry-level hardware |
| **Qwen 2.5 Instruct** | 0.5B | Q4_K_M | ~398 MB | 3 GB | High efficiency instruction-following |
| **Llama 3.2 Instruct** | 1.0B | Q4_K_M | ~840 MB | 4 GB | Balanced general knowledge and mobile reasoning |
| **Qwen 2.5 Instruct** | 1.5B | Q4_K_M | ~986 MB | 4 GB | Technical reasoning and code-related tasks |
| **Qwen 2.5 Instruct** | 3.0B | Q4_K_M | ~2.10 GB | 6 GB to 8 GB | Advanced logical reasoning and detailed synthesis |
| **Custom Models** | Variable | GGUF (All) | Device Storage | Varies | Any valid `.gguf` file imported via storage or USB |

---

## Technical Specifications

| Parameter | Specification |
| :--- | :--- |
| **Target Operating System** | Android 8.0 (API Level 26) or higher |
| **Target Architectures** | `arm64-v8a` (Primary), `x86_64` (Secondary) |
| **Native Runtime** | C++20 / JNI Bridge / `llama.cpp` Core |
| **UI Framework** | Jetpack Compose (Modern Declarative Toolkit) |
| **Local Storage Engine** | Android Room Database with SQLite |
| **Network Consumption** | 0 KB/s during inference (Completely offline) |
| **Permission Requirements** | Standard storage access (Storage Access Framework) |

---

## Installation & Deployment Procedure

1. **Acquire Package Binary**  
   Download the compiled release package directly from the repository:  
   `Evidentix-AI.apk` ([Direct Release Link](https://github.com/csibmohsin/Evidentix-Local-AI/releases/download/v1.0.0/Evidentix-AI.apk))

2. **Package Authorization**  
   If deploying outside an enterprise device manager, enable **Install unknown apps** for your respective browser or file management utility.

3. **Model Selection**  
   Launch **Evidentix Local AI**. Navigate to the **Download Models** tab to retrieve an initial lightweight model (e.g., SmolLM2 or Qwen 2.5 0.5B), or point the file picker to any existing GGUF model in storage.

4. **Inference Execution**  
   Navigate to the **Chat** interface. Text generation and conversational queries will execute locally with immediate responsiveness.

---

## Security, Privacy & Compliance Controls

- **Strict Sandbox Isolation**: Operates under standard Android application sandboxing policies.
- **Zero Outbound Data Routing**: No telemetry frameworks, analytics packages, crash-reporting daemons, or remote logging hooks are active during inference.
- **Data Destruction**: Clearing application data or uninstalling the package permanently deletes all local models, telemetry logs, and conversational records.

---

<p align="center">
  Cyber Solutions & Information Board (CSIB)
</p>
