FROM ruby:3.4-alpine

RUN apk add --no-cache build-base sqlite-dev && \
    gem install sqlite3 --platform ruby && \
    gem install gemstash

WORKDIR /gemstash

CMD ["gemstash", "start", "--no-daemonize", "--config-file", "/gemstash/config.yml"]