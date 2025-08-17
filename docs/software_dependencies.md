# Software Dependencies

## PIONEER Repository

Some installations are on the PIONEER repository, which requires access to pull from. See [how to get access](miscellaneous.md#getting-access-to-the-pioneer-repository).

---

## Development Tools

### Overview

These tools include compilers, libraries, and other utilities that facilitate software development and installation.

### Installation Guide
This guide should work for ALMA9. You can use `dnf` for ALMA9, but I prefer to work with `yum`

1 **Install yum package manager**

```
sudo dnf install yum
```

2 **Update the package index**:

```
sudo yum update
```

3 **Enable the EPEL repository**:

```
sudo yum install epel-release
```

4 **Install Development Tools and Dependencies**:

```
sudo yum groupinstall "Development Tools"
sudo yum install cmake gcc-c++ gcc screen subversion binutils libX11-devel libXpm-devel libXft-devel libXext-devel
```

5 **Install Python3**

```
sudo yum install python3-devel
```

6 **Install CMake from Source**  

If the installed CMake version is **not** `>=3.23`, (you can check with `cmake --version`) follow these steps to install CMake manually:

6.1. **Remove Old CMake (If Installed)**

```
sudo yum remove -y cmake
```

Verify removal:
```bash
cmake --version  # Should return "command not found"
```

6.2. **Install Required Dependencies**

```
sudo yum groupinstall -y "Development Tools"
sudo yum install -y gcc gcc-c++ make openssl-devel
```

6.3. **Download and Install the Latest CMake from Source**

1. **Download the latest version** (Check [Kitware's website](https://cmake.org/download/) for the latest version):
   ```
   wget https://github.com/Kitware/CMake/releases/download/v3.29.0/cmake-3.29.0.tar.gz
   ```

2. **Extract the archive**:
   ```
   tar -xvzf cmake-3.29.0.tar.gz
   cd cmake-3.29.0
   ```

3. **Build and install**:
   ```
   ./bootstrap
   make -j$(nproc)
   sudo make install
   ```

4. **Verify the New Installation**:
   ```
   cmake --version
   ```

---

## Python

---

## ROOT

### Overview

[ROOT](https://root.cern.ch/) is an open-source data analysis framework developed by CERN. It is widely used in high-energy physics for data processing, statistical analysis, visualization, and storage. It is needed for some features of Midas.

### Installation Guide
General installaiton guides are provided by ROOT at their [Installing ROOT](https://root.cern/install/) and [Building ROOT from source](https://root.cern/install/build_from_source/) pages.

## Midas

### Overview

[Midas](https://daq00.triumf.ca/MidasWiki/index.php/Main_Page) is a data acquisition system used in high-energy physics experiments.
Midas provides the following functionalities:

- Run control
- Experiment configuration
- Data readout
- Event building
- Data storage
- Slow control
- Alarm systems
- ... much more ...

### Installation Guide

For a general Midas installation, you can follow this [Linux Quick Start Guide](https://daq00.triumf.ca/MidasWiki/index.php/Quickstart_Linux).

---
