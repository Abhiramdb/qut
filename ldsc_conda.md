## Clone the LDSC repository
```bash
git clone https://github.com/bulik/ldsc.git
cd ldsc
```

## Create conda environment (as described in the LDSC repo)
```bash
conda env create --file environment.yml
conda activate ldsc
```

## Test LDSC by calling it directly
```bash
./ldsc.py -h
```

## To avoid typing full path each time, add LDSC to PATH
```bash
export PATH=/home/user/tools/ldsc:$PATH
```

## Make the PATH change permanent
```
echo 'export PATH=/home/user/tools/ldsc:$PATH' >> ~/.bashrc
source ~/.bashrc
```

## Now you can call LDSC directly
```bash
ldsc.py -h
```
