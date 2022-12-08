# PixelLibDocker

Tools to install PixelLib on Nvidia Docker for custom Training.
Follow this guide to setup [Nvidia Docker](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker).
Follow this guide to setup [Portainer](https://docs.portainer.io/start/install/server/docker/linux) to make life easier.

Run these Scripts:
 * Run \CudaAnaconda\runSetup to obtain nvidia/cuda:10.2-cudnn8-runtime-ubuntu18.04 container and install Anaconda3-2022.10-Linux-x86_64.sh in it.
 * Run \CreateEnvPixelLib\runSetup to create a new container with PixelLib environment and install python=3.7 pip setuptools jupyterlab.
 * Run \PixelLib\runSetup to create a container with Tensorflow-GPU 2.4.1 and PyTorch 1.7.1 and the stuff required to run PixelLib 0.7.1 for Training.
