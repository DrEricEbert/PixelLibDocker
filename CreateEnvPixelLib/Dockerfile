FROM ericebert/anacondacuda:latest
WORKDIR /app
COPY . .
#RUN export PATH = $PATH:~/anaconda3/bin
RUN ~/anaconda3/bin/conda create --name PixelLib python=3.7 pip setuptools jupyterlab
RUN ~/anaconda3/bin/conda env list
RUN ~/anaconda3/bin/conda init --all --system --verbose
EXPOSE 8888
