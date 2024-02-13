# qc_git_puller
Thanks to Qualcomm 's poor git server, we need to downgrade the OS to ubuntu16.04

docker run -it -v ${PWD}/work/qualcomm/8295/Code:/code  -d --name qc_git_puller ubuntu:16.04
docker exec -it qc_git_puller apt install git -y
docker exec -it qc_git_puller useradd -m -G sudo c6supper
docker exec -it -u c6supper qc_git_puller git config --global http.postBuffer 1048576000
docker exec -it -u c6supper qc_git_puller git config --global credential.helper store

docker exec -it -u c6supper qc_git_puller git clone https://qpm-git.qualcomm.com/home2/git/your_company/sa8295p-hqx-4-2-4-1_amss_standard_oem.git /code/sa8295p-hqx-4-2-4-1_amss_standard_oem
