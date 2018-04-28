#
# This is Dockerfile for tensorflow 1.3.0(with Python 3.6) on 
# nvidia/cuda(https://hub.docker.com/r/nvidia/cuda).
#
# using the follwing:
#  - NVIDIA/CUDA 8.0
#    8.0-cudnn6-runtime, 8.0-cudnn6-runtime-ubuntu16.04
#    https://gitlab.com/nvidia/cuda/blob/ubuntu16.04/8.0/runtime/cudnn6/Dockerfile
#
#

FROM nvidia/cuda:8.0-cudnn6-runtime-ubuntu16.04

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        apt-utils wget build-essential gcc \
        zlib1g-dev libcupti-dev openssl libssl-dev libbz2-dev libreadline-dev libsqlite3-dev file \
    && rm -rf /var/lib/apt/lists/*

# Python3.6 install
WORKDIR /tmp
RUN wget --no-check-certificate https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tgz \
    && tar xvfz Python-3.6.5.tgz \
    && cd Python-3.6.5 \
    && ./configure \
    && make altinstall \
    && cd /tmp && rm -rf Python-3.6.5 Python-3.6.5.tgz
ENV PYTHONIOENCODING "utf-8"

# TensorFlow & Tools install
COPY requirements.txt /tmp
RUN pip3.6 install -r /tmp/requirements.txt
RUN rm -f /tmp/requirements.txt

# Login directory
WORKDIR /root

#EOF
