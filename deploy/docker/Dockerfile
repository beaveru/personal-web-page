FROM registry.hub.docker.com/library/nginx:1.28.0-alpine-slim@sha256:39a9a15e0a81914a96fa9ffa980cdfe08e2e5e73ae3424f341ad1f470147c413

LABEL maintainer="beaverU johndoe8@duck.com"

WORKDIR /www/data

COPY . .

EXPOSE 443
EXPOSE 80

RUN useradd web
USER web

CMD ["nginx", "-g"]