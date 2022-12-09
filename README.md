# PixelLibDocker

Tools to install [PixelLib](https://github.com/ayoolaolafenwa/PixelLib) on Nvidia Docker for [custom training](https://github.com/ayoolaolafenwa/PixelLib/blob/master/Tutorials/custom_train.md).
Follow this guide to setup [Nvidia Docker](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker)
and optional setup [Portainer](https://docs.portainer.io/start/install/server/docker/linux) to make life easier.

Run these Scripts:
 * Run \CudaAnaconda\runSetup to obtain nvidia/cuda:10.2-cudnn8-runtime-ubuntu18.04 container and install Anaconda3-2022.10-Linux-x86_64.sh in it.
 * Run \CreateEnvPixelLib\runSetup to create a new container with PixelLib environment and install python=3.7 pip setuptools jupyterlab.
 * Run \PixelLib\runSetup to create a container with Tensorflow-GPU 2.4.1 and PyTorch 1.7.1 and the stuff required to run PixelLib 0.7.1 for custom training.
 
In case of Problems f.e. with current Ampere CPUs (f.e. RTX30...) use only the PixelLibCPU directory. CUDA <=10.2 has [issues](https://docs.nvidia.com/cuda/ampere-compatibility-guide/index.html) in support of the Ampere architecture You'll get a working but slower CPU training environment.
