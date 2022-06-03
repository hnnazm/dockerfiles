FROM python:3-alpine

LABEL maintainer "Muhammad Hannan <me@hnnazm.com>"

ARG VERSION

RUN python -m pip install --upgrade \
pip \
wheel \
httpie==${VERSION}

ENTRYPOINT [ "http" ]

CMD ["--help"]
