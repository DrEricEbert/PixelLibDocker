FROM ubuntu:18.04

WORKDIR /app
COPY . .
RUN apt update && apt upgrade -y && apt install --no-install-recommends -y build-essential wget apt-utils libgl1-mesa-glx libglib2.0-0
RUN wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh -O ~/anaconda.sh --no-check-certificate
RUN bash ~/anaconda.sh -b -p ~/anaconda3 -f
RUN apt clean && rm -rf /var/lib/apt/lists/*
RUN ~/anaconda3/bin/conda create --name PixelLib python=3.7 pip setuptools jupyterlab
RUN ~/anaconda3/bin/conda env list
RUN ~/anaconda3/bin/conda init --all --system --verbose
#https://pythonspeed.com/articles/activate-conda-dockerfile/
SHELL ["/root/anaconda3/bin/conda", "run", "-n", "PixelLib", "/bin/bash", "-c"]
RUN ~/anaconda3/bin/conda install -c anaconda tensorflow==2.4.1
RUN pip3 install --no-cache-dir --upgrade -r requirements.txt
EXPOSE 8888
