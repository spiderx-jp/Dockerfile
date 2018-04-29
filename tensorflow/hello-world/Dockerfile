#
# This is Dockerfile for tensorflow hello-world on
# nvidia/cuda(https://hub.docker.com/r/nvidia/cuda).
#
# using the follwing:
#  - TensorFlow 1.3.0(my build Dockerfile. 
#    https://github.com/spiderx-jp/Dockerfiles/tree/master/docker/tensorflow/1.3.0-gpu-py3
#
#

FROM spiderx-jp/tensorflow-1.3.0-gpu-py3

# tensorflow hello-world
COPY hello-world.py /root
COPY hello-world.sh /root
WORKDIR /root
RUN chmod +x hello-world.sh
ENTRYPOINT ./hello-world.sh
