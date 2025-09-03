## Clone the LDSC repository
git clone https://github.com/bulik/ldsc.git
cd ldsc

## Create conda environment (as described in the LDSC repo)
conda env create --file environment.yml
conda activate ldsc

## Test LDSC by calling it directly
./ldsc.py -h

## To avoid typing full path each time, add LDSC to PATH
export PATH=/home/user/tools/ldsc:$PATH

## Make the PATH change permanent
echo 'export PATH=/home/user/tools/ldsc:$PATH' >> ~/.bashrc
source ~/.bashrc

## Now you can call LDSC directly
ldsc.py -h
