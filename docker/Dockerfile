FROM ubuntu:14.04

RUN apt-get update
RUN apt-get install -y build-essential cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev wget unzip

WORKDIR /root
RUN wget https://github.com/opencv/opencv/archive/3.2.0.zip -O opencv.zip && unzip opencv.zip && rm opencv.zip

WORKDIR opencv-3.2.0/build
RUN cmake -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX=/usr/local ..
RUN make -j7 && make install

WORKDIR /root
ENTRYPOINT ["/bin/bash"]
