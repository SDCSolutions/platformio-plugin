FROM python:3.8-slim

ENV APP_VERSION="4.1.0" \
    APP="platformio-core"

LABEL app.name="${APP}" \
      app.version="${APP_VERSION}" \
      maintainer="Alvaro Luis Bustamante <alvarolb@thinger.io>"

RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    && rm -rf /var/lib/apt/lists/*

RUN pip install -U platformio==${APP_VERSION}

RUN groupadd --gid 1000 platformio \
  && useradd --uid 1000 --gid platformio --shell /bin/bash --create-home platformio

USER platformio

WORKDIR /home/platformio/workspace