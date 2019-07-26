FROM ubuntu:16.04

EXPOSE 8000
ENV FRONT_URL=http://localhost:5000
RUN apt-get update && apt-get install -y git curl && \
    git clone https://github.com/docker-hy/backend-example-docker.git && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    apt-get purge -y --auto-remove git curl && \ 
    rm -rf /var/lib/apt/lists/* 

WORKDIR /backend-example-docker
RUN npm install

CMD npm start