FROM ubuntu:16.04

RUN apt-get update && apt-get install -y python3 ffmpeg python3-pip wget && \
    pip3 install --upgrade yle-dl && \
    rm -rf /var/lib/apt/lists/* 

WORKDIR /videos

ENTRYPOINT [ "yle-dl" ]