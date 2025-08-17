# Environment

This section lists the environment-level software required to run the different parts of the DQM system. These are dependencies that must be installed or configured in the user's system or Conda environment. **Using the Conda environment is the faster and easier route to installation**. In the future, I may set up a docker container for developers.

---

## 1. ZeroMQ Publisher (C++)

### Required Environment Software

* **C++ compiler & build tools**: GCC/G++, make, CMake >= 3.29
* **ROOT**: Needed for reflection, plugin loading, and `TObject`-based stages and data products
* **analysis\_pipeline**: Custom C++ framework for structuring real-time data pipelines (managed by CPM; no manual setup required)
* **Intel TBB**: Used to create parallelizable pipelines (managed by CPM; no manual setup required)
* **ZeroMQ and C++ bindings**: zeromq, cppzmq, nlohmann\_json
* **MIDAS (optional)**: Required if reading data directly from MIDAS experiments

### Installation Guide

* **Development Tools**: Most tools (GCC, G++, make, CMake) are included in the [DQM dev Conda environment](resources/dqm-dev-environment.yml). If installing manually, see [miscellaneous installation notes](miscellaneous.md#development-tools).
* **ROOT**: Included in Conda environment or install via [ROOT Installation Guides](https://root.cern/install/).
* **ZeroMQ bindings**: Included in Conda environment.
* **analysis\_pipeline & Intel TBB**: Managed by CPM; no manual installation required.
* **MIDAS**: Not included in Conda; follow [Linux Quick Start Guide](https://daq00.triumf.ca/MidasWiki/index.php/Quickstart_Linux) to install.

**Notes:** Most use cases assume MIDAS input, but the system supports alternative input sources via configurable branches or processors.

---

## 2. ZMQ Receiver and FastAPI Webserver (Python)

### Required Environment Software

* **Python 3.12+**
* **pip**

### Installation Guide

* **Python & pip**: Can be installed via system package manager or included in the [DQM dev Conda environment](resources/dqm-dev-environment.yml).
* All other Python packages required by the backend (pyzmq, fastapi, uvicorn, etc.) are included in the Conda environment, so no additional manual setup is needed.

---

## 3. Data Quality Monitor Webapp (JavaScript / React)

### Required Environment Software

* **Node.js >= 20** (includes npm for installing frontend packages)

### Installation Guide

* **Node.js**: Included in the Conda environment or can be installed via [Node.js Downloads](https://nodejs.org/en/download/).
* **Frontend libraries**: React and react-plotly.js are installed locally via npm (`npm install`) and do not require environment-level setup.

---

## Conda Environment Setup

The project provides a pre-configured Conda environment `dqm_dev` that includes:

* Python 3.12 and pip
* ROOT
* analysis\_pipeline (managed by CPM)
* Intel TBB (managed by CPM)
* ZeroMQ and C++ bindings (cppzmq, zeromq, nlohmann\_json)
* Build tools: cmake, make, gcc/g++
* Node.js

### Conda Installation (if needed)

Download [Miniconda](https://docs.conda.io/en/latest/miniconda.html) (or [Anaconda](https://www.anaconda.com/products/distribution) if you prefer) for your system. Follow their setup instructions.

### Setup Instructions

```bash
conda env create -f resources/dqm-dev-environment.yml
conda activate dqm_dev
```

**MIDAS** is **not** included and must be installed separately if required.

---
