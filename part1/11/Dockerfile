FROM ubuntu:16.04

EXPOSE 8000
RUN apt-get update && apt-get install -y git
RUN git clone https://github.com/docker-hy/backend-example-docker.git
WORKDIR /backend-example-docker
COPY logs.txt .
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs
RUN npm install
CMD npm start
