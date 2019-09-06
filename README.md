# GCP
Install CUDA

GPU: NVIDIA Tesla T4
System: Ubuntu 16.04 LTS

# Prepare

Original python version 3.5, change to 3.7:

`wget https://www.python.org/ftp/python/3.7.3/Python-3.7.3.tgz`

`tar zxvf Python-3.7.3.tgz`

`cd Python-3.7.3`

`./configure --with-ssl`

`make`

`sudo make install`

`sudo rm -rf /usr/bin/python3`

`sudo rm -rf /usr/bin/pip3`

`sudo ln -s /usr/local/bin/python3.7 /usr/bin/python3.7`

`sudo ln -s /usr/local/bin/pip3.7 /usr/bin/pip3.7`

# Start

`sudo apt-get update`

`sudo apt-get upgrade`

`sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev valgrind cmake unrar gfortran python3-pip python3-dev python3-wheel swig git git-core htop g++ freeglut3-dev  libx11-dev libxmu-dev libxi-dev libglu1-mesa libglu1-mesa-dev`

`sudo apt-get install python3-pip python3-setuptools`

`sudo pip3 install --upgrade pip`

`sudo pip3 install numpy scipy matplotlib pandas seaborn sklearn lightgbm xgboost tqdm`

# CUDA

https://www.nvidia.com/Download/index.aspx

`sudo wget http://us.download.nvidia.com/tesla/418.87/NVIDIA-Linux-x86_64-418.87.00.run`

`sudo chmod +x NVIDIA-Linux-x86_64-418.87.00.run`

`sudo ./NVIDIA-Linux-x86_64-418.87.00.run`

`sudo reboot`

`nvidia-smi`

![pic0](https://github.com/Pengchengzhi/GCP/blob/master/nvidia-smi.png)

`sudo apt-get upgrade`

`sudo apt-get update`

# Anaconda

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

# OpenCV

`sudo pip3 install opencv-python`

# Pytorch

https://pytorch.org/

`conda update --all`

`conda install pytorch torchvision cudatoolkit=10.0 -c pytorch`

python3

import torch

torch.__version__













