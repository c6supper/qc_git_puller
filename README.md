# qc_git_puller
Thanks to Qualcomm 's poor git server, we need to downgrade the OS to ubuntu16.04

```
docker run -it -v ${PWD}/work/qualcomm/8295/Code:/code  -d --name qc_git_puller ubuntu:16.04
docker exec -it qc_git_puller apt install gnutls-bin git -y
docker exec -it qc_git_puller useradd -m -G sudo c6supper
docker exec -it -u c6supper qc_git_puller git config --global http.postBuffer 1048576000
docker exec -it -u c6supper qc_git_puller git config --global https.postBuffer 1048576000
docker exec -it -u c6supper qc_git_puller git config --global credential.helper store

docker exec -it -u c6supper qc_git_puller git clone https://qpm-git.qualcomm.com/home2/git/your_company/sa8295p-hqx-4-2-4-1_amss_standard_oem.git /code/hqx-4-2-4-1/sa8295p-hqx-4-2-4-1_amss_standard_oem
docker exec -it -u c6supper qc_git_puller git clone https://qpm-git.qualcomm.com/home2/git/great-wall-motor-company-limited/sa8295p-hqx-4-2-4-1_hlos_dev_la-va.git /code/hqx-4-2-4-1/sa8295p-hqx-4-2-4-1_hlos_dev_la-va
docker exec -it -u c6supper qc_git_puller git clone https://qpm-git.qualcomm.com/home2/git/great-wall-motor-company-limited/sa8295p-hqx-4-2-4-1_hlos_dev_qnx.git /code/hqx-4-2-4-1/sa8295p-hqx-4-2-4-1_hlos_dev_qnx
docker exec -it -u c6supper qc_git_puller git clone https://qpm-git.qualcomm.com/home2/git/great-wall-motor-company-limited/sa8295p-hqx-4-2-4-1_hlos_dev_qnx-api.git /code/hqx-4-2-4-1/sa8295p-hqx-4-2-4-1_hlos_dev_qnx-api
docker exec -it -u c6supper qc_git_puller git clone https://qpm-git.qualcomm.com/home2/git/great-wall-motor-company-limited/sa8295p-hqx-4-2-4-1_test_device.git /code/hqx-4-2-4-1/sa8295p-hqx-4-2-4-1_test_device
docker exec -it -u c6supper qc_git_puller git clone https://qpm-git.qualcomm.com/home2/git/great-wall-motor-company-limited/sa8295p-hqx-4-2-4-1_amss_standard_oem.git /code/hqx-4-2-4-1/sa8295p-hqx-4-2-4-1_amss_standard_oem
docker exec -it -u c6supper qc_git_puller git clone https://qpm-git.qualcomm.com/home2/git/great-wall-motor-company-limited/sa8295p-hqx-4-2-4-1_hlos_dev_la.git /code/hqx-4-2-4-1/sa8295p-hqx-4-2-4-1_hlos_dev_la
docker exec -it -u c6supper qc_git_puller git clone https://qpm-git.qualcomm.com/home2/git/great-wall-motor-company-limited/sa8295p-hqx-4-2-4-1_hlos_dev_osh.git /code/hqx-4-2-4-1/sa8295p-hqx-4-2-4-1_hlos_dev_osh
```
