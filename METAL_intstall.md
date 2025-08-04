# METAL Installation Guide

**METAL** is a meta-analysis software.  
Source code: [https://github.com/statgen/METAL](https://github.com/statgen/METAL)

This guide provides steps to install and set up METAL.

---

## 1. Clone the GitHub repository
```bash
git clone https://github.com/statgen/METAL.git
```
## 2. Build METAL
```bash
cd METAL
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make
make test
make install
```
## 3. Test METAL binary
```bash
bin/metal --help
```
## 4. Add METAL to your PATH
Edit your .bashrc:
```bash
vi ~/.bashrc
```
Add the following line at the end:
```bash
export PATH="$PATH:/home/user/METAL/build/bin"
```
Save and reload:
```bash
source ~/.bashrc
```
## 5. Verify installation
```bash
metal --help
```
