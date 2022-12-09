FROM nvidia/cuda:11.8.0-devel-ubuntu22.04

WORKDIR /app
COPY . .
RUN apt update && apt upgrade -y && apt install --no-install-recommends -y build-essential wget apt-utils libgl1-mesa-glx libglib2.0-0
RUN wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh -O ~/anaconda.sh --no-check-certificate
RUN bash ~/anaconda.sh -b -p ~/anaconda3 -f
RUN apt clean && rm -rf /var/lib/apt/lists/*
RUN ~/anaconda3/bin/conda create --name PixelLib python=3.9 pip setuptools jupyterlab
RUN ~/anaconda3/bin/conda env list
RUN ~/anaconda3/bin/conda init --all --system --verbose
#https://pythonspeed.com/articles/activate-conda-dockerfile/
SHELL ["/root/anaconda3/bin/conda", "run", "-n", "PixelLib", "/bin/bash", "-c"]
RUN ~/anaconda3/bin/conda install pytorch==1.9.0 torchvision==0.10.0 torchaudio==0.9.0 cudatoolkit=11.3 -c pytorch -c conda-forge
RUN ~/anaconda3/bin/conda install -c anaconda tensorflow
RUN pip3 install --no-cache-dir --upgrade imgaug labelme2coco pixellib
EXPOSE 8888
