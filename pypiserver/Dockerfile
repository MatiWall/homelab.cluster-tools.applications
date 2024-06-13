FROM python:3.11-alpine

RUN apk update && \
    apk add --no-cache libffi libffi-dev openssl openssl-dev && \
    pip install --no-cache-dir pypiserver[passlib]

RUN mkdir -p /data/packages

VOLUME /data/packages

EXPOSE 8080

CMD ["pypi-server", "run", "--port", "8080", "--log-file", "-", "/data/packages", "-a", ".", "-P", "."]

