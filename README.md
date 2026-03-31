<div align="center">

<img src="docs/logo.png" alt="PsyPhiClaw" width="200">

# PsyPhiClaw

**Where Psychology Meets Physiology**

An open-source, AI-powered platform for multi-modal human behavioral insight

[![GitHub](https://img.shields.io/badge/GitHub-psyphiclaw%2FPsyPhiClaw-181717?logo=github)](https://github.com/psyphiclaw/PsyPhiClaw)
[![OpenClaw](https://img.shields.io/badge/Built%20on-OpenClaw-blue?logo=claws)](https://github.com/openclaw/openclaw)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Skills: 20](https://img.shields.io/badge/Skills-20%20modules-orange)](#-skill-overview)

[English](README.md) • [中文](README-zh.md)

</div>

---

## 🎯 What is PsyPhiClaw?

**PsyPhiClaw** (Psychology + Physiology + Claw) is an open-source platform that fuses multiple human behavioral measurement modalities into a unified, AI-driven analysis engine.

We solve the **#1 pain point** in multi-modal behavioral research:

> ❌ Each device has its own software, data format, and analysis pipeline.
> ❌ Researchers spend **60% of their time** on data preprocessing and format conversion.
> ❌ No single tool can correlate signals across modalities automatically.

PsyPhiClaw provides:

- ✅ **Unified data ingestion** — Parse and normalize data from all major hardware vendors
- ✅ **Automatic temporal synchronization** — LSL / trigger-based clock alignment across modalities
- ✅ **AI-powered insight engine** — LLM-driven cross-modal correlation discovery with 6-layer guardrails
- ✅ **One-click reporting** — Publication-ready figures, statistical summaries, and HTML reports
- ✅ **Natural language interface** — Tell OpenClaw what you need, it handles the rest

---

## 📊 Supported Modalities

| Modality | Devices | Formats |
|----------|---------|---------|
| 🎭 Facial Expression | FaceReader, OpenFace | CSV, HDF5 |
| 👁️ Eye Tracking | Tobii, EyeLink, Pupil Labs, SMI | TSV, ASC, JSON, IDF |
| 🧠 EEG | Brain Products, EGI, BioSemi, EEGLAB | VHDR, RAW, SET, EDF |
| 💓 Physiology | Biopac, ADInstruments | ACQ, CSV, TXT |
| 🔴 fNIRS | NIRSport, Artinis | SNIRF, NIRX |
| 📋 Behavior Coding | Noldus Observer XT | CSV, Excel |
| 🔌 Real-time | Any LSL-compatible device | LSL streams / XDF |

---

## 🔧 Skill Overview (20 Modules)

### Data Ingestion Layer
| # | Skill | Description |
|---|-------|-------------|
| 1 | 🎭 `face-import` | FaceReader / OpenFace CSV import, AU & emotion parsing |
| 2 | 🧠 `eeg-import` | Brain Vision / EGI / EEGLAB import, MNE preprocessing, ERP analysis |
| 3 | 👁️ `eye-import` | Tobii / EyeLink / Pupil Labs data import |
| 4 | 💓 `physio-import` | Biopac / ADInstruments / generic CSV import |
| 5 | 🔴 `fnirs-import` | SNIRF / NIRSport / Artinis import, HbO/HbR conversion |
| 6 | 📋 `observer-import` | Noldus Observer XT coding data import & timeline |
| 7 | 🔌 `lsl-stream` | Lab Streaming Layer real-time stream discovery & recording |

### Analysis Layer
| # | Skill | Description |
|---|-------|-------------|
| 8 | 🧠 `eeg-analysis` | ERP components, spectral analysis, connectivity (via eeg-import) |
| 9 | 👁️ `eye-analysis` | Fixation, saccade, AOI, pupillometry analysis |
| 10 | 💓 `physio-analysis` | HRV, EDA, EMG, respiration analysis (time/freq domain) |

### Fusion Layer ⭐ (Core Differentiator)
| # | Skill | Description |
|---|-------|-------------|
| 11 | 🔗 `fusion-align` | Multi-modal temporal alignment (TTL trigger / marker / manual) |
| 12 | 📊 `fusion-correlation` | Cross-modal correlation, time-locked analysis, multimodal stats |
| 13 | 🤖 `fusion-insight` | **AI insight engine** — anomaly detection, LLM insight generation, 6-layer guardrails |

### Output Layer
| # | Skill | Description |
|---|-------|-------------|
| 14 | 📈 `visualization` | Multi-modal timeline, heatmaps, ERP topo, violin/radar/cluster plots |
| 15 | 📐 `paper-figure` | Journal-grade multi-panel figure layout (Nature/Science/APA/IEEE) |
| 16 | 📝 `analysis-report` | Manifest-based structured HTML/PDF report generation |

### Platform Layer
| # | Skill | Description |
|---|-------|-------------|
| 17 | ⚡ `batch-pipeline` | Batch processing with parallel execution & resume support |
| 18 | 🖥️ `web-dashboard` | Interactive Dash + Plotly web dashboard |
| 19 | 📚 `daily-paper` | PubMed / arXiv / Semantic Scholar literature search & digest |
| 20 | 📄 `pdf-research` | Local PDF paper reading, extraction & summarization |
| 21 | 🔧 `normalize` | Data cleaning, standardization, format conversion |

---

## 🏗️ Architecture

```
┌────────────────────────────────────────────────────────────────┐
│                      PsyPhiClaw Platform                       │
├────────────────────────────────────────────────────────────────┤
│                                                                │
│  📊 Output Layer                                               │
│  ├── 📈 Visualization (Plotly + Matplotlib, dual output)       │
│  ├── 📐 Paper Figure Layout (journal templates)                │
│  ├── 📝 Analysis Report (manifest → fill → render)             │
│  └── 🖥️ Web Dashboard (Dash + Plotly)                          │
│                                                                │
├────────────────────────────────────────────────────────────────┤
│  🤖 AI Insight Engine (Core Differentiator)                    │
│  ├── Anomaly Detection (Z-score, IQR, sliding window)          │
│  ├── Cross-Modal Correlation (Pearson, Spearman, dynamic)      │
│  ├── LLM Insight Generation (OpenAI API)                       │
│  ├── 6-Layer Guardrails (integrity, significance, effect size, │
│  │   causality, multiple comparison, hallucination check)       │
│  └── Multimodal Summary (Markdown + JSON)                      │
│                                                                │
├────────────────────────────────────────────────────────────────┤
│  🔗 Fusion Layer                                               │
│  ├── Session Manager (MultiModalSession HDF5)                  │
│  ├── TTL Trigger Alignment                                     │
│  ├── Event Marker Alignment                                    │
│  ├── Resample & Sync (linear / nearest / ffill)                │
│  └── LSL Real-Time Streaming                                   │
│                                                                │
├────────────────────────────────────────────────────────────────┤
│  📥 Data Ingestion Layer                                       │
│  ├── FaceReader CSV · OpenFace · FACS                          │
│  ├── Tobii TSV · EyeLink ASC · Pupil Labs                     │
│  ├── Brain Vision VHDR · EGI · EEGLAB SET                     │
│  ├── Biopac ACQ · ADInstruments LabChart                      │
│  ├── fNIRS SNIRF · NIRSport · Artinis                         │
│  ├── Observer XT Coding + Video Sync                           │
│  └── Lab Streaming Layer (LSL) + XDF                           │
│                                                                │
└────────────────────────────────────────────────────────────────┘
         Built on OpenClaw — fully compatible with all plugins & channels
```

---

## 🚀 Quick Start

### Option A: Install as OpenClaw Skills

```bash
# If you already have OpenClaw installed
git clone https://github.com/psyphiclaw/openclaw.git
cd openclaw

# Copy all PsyPhiClaw skills to your OpenClaw workspace
cp -r skills/psyphiclaw-* ~/.openclaw/skills/

# Restart OpenClaw and use natural language:
# "Please analyze the FaceReader data in /data/project_01/"
```

### Option B: Full Installation (Fork of OpenClaw)

```bash
# Prerequisites
- Python 3.10+
- Node.js 24+
- CUDA GPU (optional, for real-time processing)

# Clone and install
git clone https://github.com/psyphiclaw/openclaw.git
cd openclaw
pnpm install
pnpm ui:build && pnpm build
pnpm openclaw onboard --install-daemon
pnpm gateway:watch

# Install Python dependencies
pip install mne pandas numpy scipy plotly matplotlib seaborn neurokit2 pylsl jinja2
```

### Usage via Natural Language

Once OpenClaw is running with PsyPhiClaw skills, you can simply say:

```
📌 Import the FaceReader CSV from /data/subject_01/ and show me the VAD timeline.

📌 Import the EEG recording, apply bandpass filter 0.1-40Hz, and extract P300 components.

📌 Align the FaceReader and EEG data using TTL triggers from the experiment.

📌 Generate a cross-modal correlation analysis between facial expressions and EEG signals.

📌 Detect anomalies in the multimodal session and generate an AI insight report.

📌 Create a publication-ready multi-panel figure for the journal Nature.
```

---

## 📈 Project Stats

| Metric | Value |
|--------|-------|
| Total Skills | 20+ |
| Python Code | 18,000+ lines |
| Supported Devices | 15+ |
| Supported Formats | 20+ |
| Output Formats | PNG, HTML, PDF, SVG, HDF5, JSON, Markdown |

---

## 🗺️ Roadmap

- [x] **Phase 1** — Dual-modal MVP (FaceReader + EEG + Fusion)
- [x] **Phase 2** — Multi-modal expansion (Eye, Physio, fNIRS, AI Insight, Literature)
- [x] **Phase 3** — Platform (LSL, Observer XT, Paper Layout, Batch, Dashboard, Normalize)
- [ ] **Phase 4** — Real-world validation with actual research datasets
- [ ] **Phase 5** — Preprint publication & ClawHub release
- [ ] **Phase 6** — Community building & plugin ecosystem

---

## 🆚 Why PsyPhiClaw?

| Dimension | Existing Tools | PsyPhiClaw |
|-----------|---------------|------------|
| Multi-modal fusion | ❌ None | ✅ Core feature |
| AI-driven insights | ❌ None | ✅ LLM + 6-layer guardrails |
| Vendor compatibility | ❌ Single-vendor | ✅ 15+ devices |
| Natural language interface | ❌ GUI only | ✅ OpenClaw integration |
| Publication-ready output | Partial | ✅ Journal templates |
| Open source | Partial | ✅ MIT License |

---

## 📄 Citation

```bibtex
@preprint{psyphiclaw2026,
  title={PsyPhiClaw: An Integrated AI Workflow Platform for Multi-Modal Human Behavioral Insight},
  author={Yang, Penghan},
  year={2026},
  doi={TBD}
}
```

---

## 📄 License

PsyPhiClaw is released under the [MIT License](LICENSE).

## 🙏 Acknowledgements

- [OpenClaw](https://github.com/openclaw/openclaw) — AI agent framework
- [MNE-Python](https://mne.tools/) — EEG & fNIRS analysis
- [NeuroKit2](https://neurolkit.github.io/) — Physiological signal processing
- [OpenFace](https://github.com/TadasBaltrusaitis/OpenFace) — Facial behavior analysis
- [EthoClaw](https://github.com/penciler-star/EthoClaw) — Inspiration for the OpenClaw skill architecture

---

<div align="center">

**PsyPhiClaw** — Where Psychology Meets Physiology

Built with ❤️ by the Noldus community

</div>
