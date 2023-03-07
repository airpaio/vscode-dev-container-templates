ARG RUN_DEP="make curl git vim zip unzip"

FROM golang:1.19-bullseye as base

ARG BUILD_DEP
ARG RUN_DEP

RUN apt-get update && \
    apt-get install -y ${RUN_DEP}

FROM base as dev

# install aws cli
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    ./aws/install && \
    rm -r awscliv2.zip aws/