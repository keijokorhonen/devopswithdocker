FROM node:alpine as build-stage

RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/frontend-example-docker.git

WORKDIR /frontend-example-docker
RUN npm install && npm run build

FROM node:alpine

EXPOSE 5000
COPY --from=build-stage /frontend-example-docker/dist ./dist

RUN npm install -g serve && \
    adduser -D app && \
    chown -R app dist

USER app

CMD serve -s -l 5000 dist