# Miscellaneous

## Additional Notes

If you're feeling desperate (or perhaps lucky), you can sift through [Jack Carlton's work notes](https://jaca230.github.io/joplin_notes_page/). **I warn you that these are not well organized and contain lots of information not about this project**. However, they do contain some documentation of my assembly and troubleshooting of this project. For this particular project, there was not much trial and error so any entries regarding DQM development will be few and far between.

---

## Initialism Cheatsheet

See the [g-2 modified DAQ's initialism cheatsheet](https://jaca230.github.io/teststand_daq_manual/miscellaneous_info/#initialism-cheatsheet), many of the initialisms are relevant to the DQM.

---

## Networking Tutorial

See the [g-2 modified DAQ's networking tutorial](https://jaca230.github.io/teststand_daq_manual/networking/) for basics. There are many additional (and probably better) online resources as well.

---

## Useful Midas Information

See the [g-2 modified DAQ's midas information page](https://jaca230.github.io/teststand_daq_manual/midas/) for some general midas tips. There is much more information available on TRIUMF's [Midas Wiki](https://daq00.triumf.ca/MidasWiki/index.php/Main_Page) page.

---

## Getting Access to the PIONEER repository

See the g-2 modified DAQ manual's [accessing the pioneer repository section](https://jaca230.github.io/teststand_daq_manual/software_dependencies/#pioneer-experiment-repositories) and [setting up a github ssh token section](https://jaca230.github.io/teststand_daq_manual/software_dependencies/#setting-up-a-github-ssh-token-on-rhel79-systems).

---

## Port Forwarding an SSH Connection

See the [g-2 modified DAQ's port forwarding an SSH connection section](https://jaca230.github.io/teststand_daq_manual/miscellaneous_info/#port-forwarding-an-ssh-connection).

---

## Using Screens in Linux

See the [g-2 modified DAQ's using screens in linux page](https://jaca230.github.io/teststand_daq_manual/miscellaneous_info/#using-screens-in-linux).

---

## Development Tools

### Installation Guide (Detailed)
Installing development tools depends on your system. This guide should work for ALMA9. You can use `dnf` for ALMA9, but I prefer to work with `yum`

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

```
