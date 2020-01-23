FROM python:3.7-slim

ENV APP_VERSION="4.1.0" \
    APP="platformio-core"

LABEL app.name="${APP}" \
      app.version="${APP_VERSION}" \
      maintainer="Alvaro Luis Bustamante <alvarolb@thinger.io>"

RUN pip install -U platformio==${APP_VERSION} && \
    mkdir -p /workspace && \
    mkdir -p /.platformio && \
    chmod a+rwx /.platformio

USER 1001

WORKDIR /workspace

ENTRYPOINT ["platformio"]