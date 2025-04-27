ARG RUN_DEP="make curl git vim zip unzip"

FROM pandoc/latex:3.6.4.0-alpine as base

ARG BUILD_DEP
ARG RUN_DEP

RUN apk update && \
    apk add ${RUN_DEP}

FROM base as dev

# install aws cli
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    ./aws/install && \
    rm -r awscliv2.zip aws/
