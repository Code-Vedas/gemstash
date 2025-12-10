FROM ruby:3.4-slim

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      build-essential \
      libsqlite3-dev \
      pkg-config \
      ca-certificates && \
    rm -rf /var/lib/apt/lists/*

RUN gem install sqlite3 && \
    gem install gemstash

WORKDIR /gemstash

CMD ["gemstash", "start", "--no-daemonize", "--config-file", "/gemstash/config.yml"]
