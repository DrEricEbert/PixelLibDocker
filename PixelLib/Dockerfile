FROM ericebert/pixellibenv:latest
WORKDIR /app
COPY requirements.txt .

#https://pythonspeed.com/articles/activate-conda-dockerfile/
SHELL ["/root/anaconda3/bin/conda", "run", "-n", "PixelLib", "/bin/bash", "-c"]
RUN apt update
RUN apt install apt-utils -y
RUN apt install libgl1-mesa-glx -y
RUN apt install libglib2.0-0 -y
RUN ~/anaconda3/bin/conda install -c anaconda tensorflow-gpu==2.4.1
RUN pip3 install --no-cache-dir --upgrade -r requirements.txt
#RUN pip3 uninstall scikit-image
RUN pip3 install --no-input scikit-image==0.14.2

EXPOSE 8888
