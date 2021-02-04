# xr-sw-update Ansible Playbook usage

Prior to running the playbook, create a tar file that contains all the packages/SMU to be added and calculate the tar file md5.

In the below example syntax replace package.tar with the file name that refers to the tar file that contain all the needed packages/SMU. This file shall be accessible 
from the Ansible controller where the Playbook is launched from.

When calling the ANsible playbook -e/Extra-vars are used to provide the package /tar file and it's md5 checksum value as a parameter/value which will be used in the 
playbbok to check the file integrity after it's copied to the device harddisk

playbook.yml refers to the playbook (asr9k-sw-install.yml provided in this repo).

ansible-playbook <playbook.yml>  -e "pkg_tar_file=package.tar pkg_tar_file_md5=6e396a7ff9f1f7ccc35c57e2875a1eb8"

ansible-playbook asr9k-sw-install.yml -vvvv -e "pkg_tar_file=ASR9K-532-24SMU.tar pkg_tar_file_md5=6e396a7ff9f1f7ccc35c57e2875a1eb8"
