# PsyPhiClaw

<p align="center">
  <img src="docs/logo.png" alt="PsyPhiClaw" width="200">
</p>

<p align="center">
  <strong>PsyPhiClaw</strong> — An open-source AI-powered platform for multi-modal human behavioral insight
</p>

<p align="center">
  <a href="#features">Features</a> • <a href="#architecture">Architecture</a> • <a href="#installation">Installation</a> • <a href="#roadmap">Roadmap</a> • <a href="#contributing">Contributing</a>
</p>

---

**PsyPhiClaw** (Psychology + Physiology + Claw) is an open-source platform that integrates multiple human behavioral measurement modalities — facial expressions, eye tracking, EEG, physiological signals (EDA, ECG, EMG, respiration), and fNIRS — into a unified, AI-driven analysis and insight engine.

Built on [OpenClaw](https://github.com/openclaw/openclaw), PsyPhiClaw inherits all features of OpenClaw and is fully compatible with its plugin ecosystem and communication channels.

## Why PsyPhiClaw?

Modern behavioral research increasingly relies on **multi-modal data fusion** — combining psychological and physiological measurements to build a holistic picture of human cognition, emotion, and behavior. However, researchers face a critical bottleneck:

> **Each device has its own proprietary software, data format, and analysis pipeline.** Researchers spend up to 60% of their time on data preprocessing, format conversion, and temporal alignment — leaving little time for actual scientific discovery.

PsyPhiClaw solves this by providing:

- **Unified data ingestion**: Parse and normalize data from all major hardware vendors
- **Automatic temporal synchronization**: LSL / trigger-based clock alignment across modalities
- **AI-powered insight generation**: Multi-modal correlation analysis with LLM-driven natural language insights
- **One-click reporting**: Publication-ready figures, statistical summaries, and analysis reports

## Features

### 🎭 Facial Expression Analysis
- Import and analyze **FaceReader** output (Action Units, emotion dimensions)
- Compatible with OpenFace, FACS, and other expression analysis tools

### 👁️ Eye Tracking
- Import data from **Tobii**, **SMI**, **EyeLink**, and **Pupil Labs**
- Fixation analysis, saccade detection, heatmaps, and areas of interest (AOI)

### 🧠 EEG Signal Processing
- Import **Brain Vision**, **EGI**, **BioSemi**, and **EEGLAB** formats
- Preprocessing pipeline powered by **MNE-Python**
- ERP analysis, spectral analysis, and connectivity metrics

### 💓 Physiological Signals
- Import **Biopac** (ACQ), **ADInstruments**, and raw biosignal formats
- EDA, ECG, EMG, respiration, and heart rate variability (HRV) analysis
- Powered by **NeuroKit2** and **BioSPPy**

### 🔴 fNIRS
- Import **NIRSport**, **Artinis**, and **SNIRF** format data
- Hemodynamic response analysis and channel-level visualization

### 🔗 Multi-Modal Fusion (Core)
- Cross-modal temporal alignment and synchronization
- Correlation analysis across modalities
- AI-driven automatic insight detection
- Interactive multi-modal timeline visualization

### 📊 Reporting & Visualization
- Publication-ready figure generation (violin plots, cluster plots, heatmaps, etc.)
- Automated statistical analysis reports
- LLM-powered natural language insight summaries
- One-click experiment report generation

### 📚 Knowledge & Literature
- Local PDF paper ingestion and summarization
- Automated literature search (arXiv, PubMed, Google Scholar)
- Scheduled daily paper alerts

## Architecture

```
┌──────────────────────────────────────────────────────────┐
│                   PsyPhiClaw Platform                     │
├──────────────────────────────────────────────────────────┤
│                                                          │
│  📊 Visualization & Reporting                            │
│  ├── Interactive multi-modal timeline                    │
│  ├── AI insight dashboard                                │
│  └── Publication-ready report generation                 │
│                                                          │
├──────────────────────────────────────────────────────────┤
│  🧠 AI Insight Engine                                    │
│  ├── Multi-modal correlation analysis                    │
│  ├── LLM natural language insight generation             │
│  ├── Automatic anomaly detection                         │
│  └── Statistical analysis automation                     │
│                                                          │
├──────────────────────────────────────────────────────────┤
│  🔗 Fusion Layer                                         │
│  ├── Temporal synchronization (LSL / TTL triggers)       │
│  ├── Data standardization pipeline                       │
│  └── Cross-modality event alignment                      │
│                                                          │
├──────────────────────────────────────────────────────────┤
│  📥 Data Ingestion Layer                                 │
│  ├── FaceReader CSV / OpenFace                           │
│  ├── Tobii TSV / SMI IDF / EyeLink ASC                   │
│  ├── Brain Vision RAW / EGI / EEGLAB SET                │
│  ├── Biopac ACQ / ADInstruments                         │
│  ├── fNIRS NIRSport / Artinis / SNIRF                   │
│  ├── Observer XT coding + video sync                    │
│  └── Lab Streaming Layer (LSL) real-time support         │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Supported Devices & Formats

| Modality | Devices | Data Formats |
|----------|---------|-------------|
| Facial Expression | FaceReader, OpenFace | CSV, HDF5 |
| Eye Tracking | Tobii, SMI, EyeLink, Pupil Labs | TSV, IDF, ASC, JSON |
| EEG | Brain Products, EGI, BioSemi | RAW, EDF, SET, VHDR |
| Physiology | Biopac, ADInstruments | ACQ, CSV |
| fNIRS | NIRSport, Artinis | SNIRF, NIRX |
| Behavior Coding | Observer XT | CSV, AVI sync |
| Real-time | Any LSL-compatible device | LSL streams |

## Roadmap

### Phase 1: Dual-Modal MVP (Q2 2026)
- [ ] FaceReader CSV import & expression timeline visualization
- [ ] EEG (Brain Vision) import & MNE preprocessing pipeline
- [ ] Cross-modal temporal alignment
- [ ] Basic statistical analysis (ERP + expression time-locked)
- [ ] Initial OpenClaw skill integration

### Phase 2: Multi-Modal Expansion (Q3 2026)
- [ ] Eye tracking data import (Tobii, EyeLink)
- [ ] Physiological signal processing (NeuroKit2)
- [ ] LLM-driven multi-modal insight engine
- [ ] Automatic anomaly detection
- [ ] Interactive Dash dashboard

### Phase 3: Platform (Q4 2026)
- [ ] fNIRS data support
- [ ] LSL real-time streaming support
- [ ] Observer XT coding data compatibility
- [ ] Publication-ready report auto-generation
- [ ] Web UI for non-technical users
- [ ] Plugin marketplace (ClawHub integration)

## Installation

### Prerequisites
- Python 3.10+
- Node.js 24+ (for OpenClaw)
- NVIDIA GPU with CUDA (recommended for real-time processing)

### Quick Start

```bash
# Clone the repository
git clone https://github.com/psyphiclaw/PsyPhiClaw.git
cd PsyPhiClaw

# Install Python dependencies
pip install -e .

# Install OpenClaw (if not already installed)
# See https://docs.openclaw.ai for detailed instructions

# Copy skills to your OpenClaw workspace
cp -r skills/ethoclaw-* ~/.openclaw/skills/
```

### Optional: GPU Acceleration

```bash
# For EEG/fNIRS real-time processing
pip install torch --index-url https://download.pytorch.org/whl/cu121
```

## Usage

```python
# Import and analyze multi-modal data
from psyphiclaw import Session

session = Session()
session.load_facereader("data/subject_01/face_reader_output.csv")
session.load_eeg("data/subject_01/recording.vhdr")
session.load_eye_tracking("data/subject_01/tobii_export.tsv")

# Automatic temporal alignment
session.align(modalities=["face", "eeg", "eye"], method="trigger")

# Generate multi-modal insight report
session.analyze(method="auto")
session.export_report("results/subject_01_report.pdf")
```

Or via OpenClaw natural language:

```
Please analyze the multi-modal data in /data/subject_01/,
including FaceReader output, EEG recording, and Tobii eye tracking data.
Align the timelines and generate an insight report.
```

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Citation

If you use PsyPhiClaw in your research, please cite:

```bibtex
@preprint{psyphiclaw2026,
  title={PsyPhiClaw: An Integrated AI Workflow Platform for Multi-Modal Human Behavioral Insight},
  author={Yang, Penghan},
  year={2026},
  doi={TBD}
}
```

## License

PsyPhiClaw is released under the [MIT License](LICENSE).

## Acknowledgements

PsyPhiClaw is built upon the excellent work of the open-source community. We would like to thank:

- [OpenClaw](https://github.com/openclaw/openclaw) — AI agent framework
- [MNE-Python](https://mne.tools/) — EEG/fNIRS analysis
- [NeuroKit2](https://neurolkit.github.io/) — Physiological signal processing
- [DeepLabCut](https://github.com/DeepLabCut/DeepLabCut) — Pose estimation
- [OpenFace](https://github.com/TadasBaltrusaitis/OpenFace) — Facial behavior analysis

---

<p align="center">
  <i>PsyPhiClaw — Where Psychology Meets Physiology</i>
</p>
```
