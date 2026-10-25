# Adit Pratap Singh Rathour
**Systems Engineer · AI Orchestrator · Linux Internals**

I design automated build pipelines, debug low-level boot sequences, and run local LLMs as offline engineering assistants. I don't memorize syntax — I architect solutions and verify them against real hardware.

[![AeroKernel CI](https://github.com/aditrathour07/AeroKernel-sweet/actions/workflows/AOSP%20Builder.yml/badge.svg)](https://github.com/aditrathour07/AeroKernel-sweet/actions)
[![AeroKernel release](https://img.shields.io/github/v/release/aditrathour07/AeroKernel-sweet?include_prereleases&label=AeroKernel%20release)](https://github.com/aditrathour07/AeroKernel-sweet/releases)
[![Base](https://img.shields.io/badge/base-Linux%204.14%20LTS%20%7C%20sm6150-0078D6)](https://github.com/aditrathour07/AeroKernel-sweet)

## 🔭 Currently
- **AeroKernel** — custom Android kernel for sm6150 (sweet/sweetin): cloud CI, AnyKernel3 packaging, KernelSU build integration.
- **Boot-regression forensics** — bisecting an init-stage bootloop with `dmesg`/`pstore` analysis and F2FS superblock evidence.
- **Local Systems-Agent** — offline GGUF LLM fine-tuned for kernel-log triage.

## 🛠 Core Competencies — claim → proof
| Competency | Proof |
|---|---|
| CI/CD & cloud build orchestration | [AeroKernel pipeline](https://github.com/aditrathour07/AeroKernel-sweet/actions) — GitHub Actions cross-compiles a 4.14 kernel (Neutron Clang + GCC cross pair), packages flashable zips, publishes releases |
| Linux kernel & Android boot chain | Forked, configured (`sweet_defconfig`), built and flash-packaged a kernel; traced bootloader → kernel → init → zygote failures through `dmesg` |
| Low-level debugging & forensics | [Bootloop case study](#-bootloop-forensics--a-public-case-study) — ramoops/pstore extraction, `fsck.f2fs` superblock versioning, device-mapper failure analysis |
| AI infrastructure | Fine-tuned + quantized a GGUF model on Colab for offline kernel-log triage; context engineering for codebase-scale analysis |
| Shell & build systems | Bash automation, Kbuild flags (`LLVM_IAS=1`, `KCFLAGS`), toolchain pinning, AnyKernel3 installer scripting |

## 🚀 Featured Lab Projects

### 🌬️ AeroKernel — automated Android kernel pipeline
Custom fork of Linux 4.14 (Vantom-based) for Redmi Note 10 Pro / Pro Max.
- Engineered a **GitHub Actions CI/CD pipeline**: toolchain provisioning, parallel make, artifact + release publishing.
- Automated **AnyKernel3 flashable packaging** (boot/dtbo/dtb handling) with installer-banner rebranding via `sed` injection.
- Integrated **KernelSU-Next** at build time; validated hook initialization via kernel-log analysis.
- Running a **controlled bisect** on an init-stage boot regression (dtbo vs compiler vintage), commit by commit.

📦 [Repository](https://github.com/aditrathour07/AeroKernel-sweet) · [v1.0 release](https://github.com/aditrathour07/AeroKernel-sweet/releases)

### 🤖 Local Systems-Agent (GGUF)
Offline, privacy-first LLM specialized in low-level systems triage.
- Fine-tuned on kernel mailing-list & boot-log corpora via Google Colab; quantized to GGUF for local inference.
- Used for `dmesg`/`pstore` triage: isolating panic signatures, driver probe failures, SELinux/AVB anomalies.

📦 [Model card](https://github.com/aditrathour07/kernel-debug-llm)

### 🩺 Bootloop Forensics — a public case study
How a "green CI + flashable zip" can still bootloop — and how to prove why:
- Eliminated KernelSU as the culprit via a **rootless probe build** (bisect variable A).
- Proved the kernel reaches Android `init` with all drivers healthy (~2.5 s) using recovery-captured `dmesg`.
- Located the failure window at device-mapper logical-partition updates (~3.9 s) → dtbo/ROM-layout hypothesis → **boot-only flash test** (v1.2).

📄 [Full lab note](https://github.com/aditrathour07/lab-notes)

## 🧰 Toolbox
Linux (Debian/Arch/Nix families) · Bash · Python · Git & GitHub Actions · Kbuild/Make · Clang/LLVM · AnyKernel3 · fastboot/adb · recovery internals (OrangeFox/TWRP) · Colab & LLM quantization

## 📬 Contact
Open to DevOps / SRE / embedded-Android internships and freelance Linux automation work.
💬 Telegram: [Adit Pratap Singh Rathour](t.me/cupid_2911)
