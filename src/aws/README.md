# Instructions:

## 1. Launch an EC2 instance via gui

Any small instance should be fine. Amazon linux isn't necessary but some commands may need to be reworked on different OSes.

### Add Entries to Security Group
- Add an inbound rule for HTTP so that port 80 is opened up.
- Add an inbound rule for postgresql so that port 5432 is opened up.

Login to the node for the rest of the steps:
`ssh -i <key.pem> ec2-user@<ip>`

## 2. Install initial dependencies

`sudo yum install git`

## 3. Clone project code

### Example 1:
`git clone https://github.com/twlim1/260_capstone.git`

### Example 2, with implied ssh key:
`git clone git@github.com:twlim1/260_capstone.git`

## 4. Run project script
```
cd 260_capstone/src/aws
./containermanage.sh -h
```

### To create fresh images and containers
- Download all the models into 260_capstone/models/ folders
```
260_capstone/models/
    ├───AC
    ├───AI
    ├───AV
    ├───CI
    ├───II
    ├───PR
    ├───SC
    └───UI
```
- Pre-trained and fine-tuned models can be found on Google Drive here
```
https://drive.google.com/drive/u/1/folders/1pCKXd2jkf2EZjvlAnzFXNMxyaTsRDxau
```
- After placing the models in the folders, run the following command to create images and containers
```
./containermanage.sh fresh
```
Run the following commands to populate a database, tables and test data
```
./containermanage.sh connect dba
python dba_scripts/db_init.py
python dba_scripts/data_download_cve.py --test_mode
# if no GPU is exposed to dba container (default DBA container)
python dba_scripts/batch_prediction.py 
# if GPU is exposed to dba container (see containermanage.sh comment to enable gpu)
python dba_scripts/batch_prediction.py --use_gpu
```
- To predict severity of cybersecurity threat from user input description
```
./containermanage.sh connect dba
python dba_scripts/single_prediction.py --description "A flaw was found in libwebp in versions before ..."
```