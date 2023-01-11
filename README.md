# USRP_testing

## Firstly clone the OAI repo

```bash 
git clone https://gitlab.eurecom.fr/oai/openairinterface5g.git
```

```bash
git checkout develop
```
```bash
cd openairinterface5g/cmake_targets/tools/
```
```bash
vim build_helper
```
Now change the version of libuhd to 3.15.0

## Now build the gNB
```bash
cd ../
./build_oai -I -w USRP --eNB --UE --nrUE --gNB
```

> Binaries will be built under the directory cmake_target/ran_build/build

So binaries `nr-softmodem` & `nr-uesoftmodem` will be created

```bash
cd ~/openairinterface5g/targets/PROJECTS/GENERIC-NR-5GC/CONF/
```
* Now check the USRP file that you want to use according to your requirement
* Open the conf file and change the value of the identifiers as per the Core

Now try to ping the ip of AMF
```bash
ping ping 192.168.70.132
```
## Now run the final command of USRP
```bash
cd ~/openairinterface5g/cmake_targets/ran_build/build/
```
Now run the command of running the USRP
```bash
sudo ./nr-softmodem -E --sa -O ../../../targets/PROJECTS/GENERIC-NR-5GC/CONF/gnb.sa.band78.fr1.106PRB.usrpb210.conf --continous --tx
```
Now check the logs AMF will be connected.
