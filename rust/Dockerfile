ARG RUN_DEP="make curl git vim zip unzip"

FROM rust:1.88-bullseye AS base

RUN apt-get update && \
    apt-get install -y ${RUN_DEP}

FROM base AS dev

# install aws cli
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    ./aws/install && \
    rm -rf awscliv2.zip aws/