# DNAnexus Login via HPC

## 1. Load required modules

```bash
module load GCCcore/14.2.0
module load Python/3.13.1
```
## 2. Install DNAnexus Python
```bash
pip install dxpy
```
## 3. Authenticate with DNAnexus
```bash
dx login
```
## 3. Check status
```bash
dx ls
```
