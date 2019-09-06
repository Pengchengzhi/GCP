# Initialize Computer Engine on Google Cloud Platform

A guide to install CUDA, Anaconda, OpenCV, Pytorch and build environment for Computer Vision.

* GCP: [Google Cloud Platform](https://cloud.google.com/)

* My GPU: NVIDIA Tesla T4

* My System: Ubuntu 16.04 LTS

## Create VM instance

To be done

## Preparing

Get some essential packages and updates.
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev valgrind cmake unrar gfortran python3-pip python3-dev python3-wheel swig git git-core htop g++ freeglut3-dev  libx11-dev libxmu-dev libxi-dev libglu1-mesa libglu1-mesa-dev
```
Original python version is python3.5, change to python3.7:

```
wget https://www.python.org/ftp/python/3.7.3/Python-3.7.3.tgz
tar zxvf Python-3.7.3.tgz
cd Python-3.7.3
./configure --with-ssl
make
sudo make install
```

Remove previous soft link and add new soft link:

```
sudo rm -rf /usr/bin/python3
sudo rm -rf /usr/bin/pip3
sudo ln -s /usr/local/bin/python3.7 /usr/bin/python3.7
sudo ln -s /usr/local/bin/pip3.7 /usr/bin/pip3.7
```
Get packages
```
sudo apt-get install python3-pip python3-setuptools
sudo pip3 install --upgrade pip
sudo pip3 install numpy scipy matplotlib pandas seaborn sklearn lightgbm xgboost tqdm
```

## Install CUDA

Find your package at [Nvidia offical website](https://www.nvidia.com/Download/index.aspx).
```
cd ..
sudo wget http://us.download.nvidia.com/tesla/418.87/NVIDIA-Linux-x86_64-418.87.00.run
sudo chmod +x NVIDIA-Linux-x86_64-418.87.00.run
sudo ./NVIDIA-Linux-x86_64-418.87.00.run
sudo apt-get update
sudo apt-get upgrade
```
Then reboot and check if successfully installed.

`nvidia-smi`

My result:

![pic0](https://github.com/Pengchengzhi/GCP/blob/master/nvidia-smi.png)

Driver Version: 418.87.00

CUDA Version: 10.1

## Install Anaconda

`wget https://repo.anaconda.com/archive/Anaconda3-2019.07-Linux-x86_64.sh`

`bash Anaconda3-2019.07-Linux-x86_64.sh`

source ~/.bashrc

jupyter notebook --generate-config

vim /home/usr/.jupyter/jupyter_notebook_config.py

c = get_config()

c.NotebookApp.ip = '*'

c.NotebookApp.open_browser = False

c.NotebookApp.port = <Port Number>

Can't open

http request, not https

close all vpn

close chrome plugin

## Install OpenCV

`sudo pip3 install opencv-python`

## Install Pytorch

https://pytorch.org/

`conda update --all`

`conda install pytorch torchvision cudatoolkit=10.0 -c pytorch`

python3

import torch

torch.__version__













