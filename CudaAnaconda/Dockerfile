FROM nvidia/cuda:10.2-cudnn8-runtime-ubuntu18.04

WORKDIR /app
COPY . .
RUN apt update && apt upgrade -y && apt install --no-install-recommends -y build-essential wget
RUN wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh -O ~/anaconda.sh
RUN bash ~/anaconda.sh -b -p ~/anaconda3 -f
RUN apt clean && rm -rf /var/lib/apt/lists/*
