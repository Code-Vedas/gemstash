# SPDX-License-Identifier: MIT
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

LABEL org.opencontainers.image.title="Gemstash"
LABEL org.opencontainers.image.description="Private RubyGems server for caching, mirroring, and hosting private gems"
LABEL org.opencontainers.image.source="https://github.com/bundler/gemstash"
LABEL org.opencontainers.image.licenses="MIT"
LABEL org.opencontainers.image.vendor="Codevedas Inc."
LABEL org.opencontainers.image.url="https://github.com/Code-Vedas/gemstash/pkgs/container/gemstash"

WORKDIR /gemstash

CMD ["gemstash", "start", "--no-daemonize", "--config-file", "/gemstash/config.yml"]
