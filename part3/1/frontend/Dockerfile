FROM ubuntu:16.04

EXPOSE 5000
ENV API_URL=http://localhost:8000
RUN apt-get update && apt-get install -y git curl && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    apt-get purge -y --auto-remove git curl && \ 
    rm -rf /var/lib/apt/lists/* 

WORKDIR /frontend-example-docker

RUN npm install
CMD npm start