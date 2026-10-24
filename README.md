# 👋 Hi, I'm Adit

I am a Systems Engineer and AI Orchestrator specializing in Linux internals, CI/CD automation, and embedded Android architecture. I build automated pipelines, debug low-level boot sequences, and leverage local LLMs for systems-level troubleshooting.

### 🛠️ Core Competencies
- **Systems & OS:** Linux Kernel Architecture, Android Boot Process (Bootloader -> Kernel -> Init -> Zygote), Device Tree (DTS) manipulation.
- **DevOps & CI/CD:** GitHub Actions, YAML automation, Cloud Compute orchestration, Artifact management.
- **AI Infrastructure:** Fine-tuning and quantizing local GGUF LLMs for specialized technical debugging (C-code, kernel panics).
- **Scripting:** Bash, Python, Makefiles.

### 🚀 Featured Lab Projects

#### 🌬️ AeroKernel (Automated Android Kernel Pipeline)
A custom fork of the Linux 4.14 kernel for the sm6150 (Redmi Note 10 Pro) architecture.
- Engineered a fully automated **GitHub Actions CI/CD pipeline** to cross-compile the kernel in the cloud using Neutron Clang.
- Automated **AnyKernel3** packaging and zip-signing.
- Conducted deep-dive forensic debugging using `dmesg` and `pstore` ramoops to trace `init` failures and DTBO mismatches.
- [View Repository](https://github.com/aditrathour07/AeroKernel-sweet)

#### 🤖 Local Systems-Agent (GGUF LLM)
A custom-trained, offline AI model specialized in low-level systems engineering.
- Fine-tuned a base LLM on Linux kernel mailing lists, C-code memory management, and Android boot logs.
- Quantized to GGUF format for local, privacy-first inference to parse complex `dmesg` dumps without relying on cloud APIs.
- [View Documentation](#)
