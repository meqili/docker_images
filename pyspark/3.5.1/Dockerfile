FROM ubuntu:24.04
LABEL maintainer="Qi Li (liq3@email.chop.edu)"

ENV PYSPARK_VERSION 3.5.1
ENV DEBIAN_FRONTEND=noninteractive

# Update and install dependencies
RUN apt-get update && apt-get install -y \
    python-is-python3 \
    python3-pip \
    default-jre \
    python3-venv \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Create a virtual environment and install Python packages
RUN python3 -m venv /opt/venv \
    && /opt/venv/bin/pip install --upgrade pip \
    && /opt/venv/bin/pip install pyspark==${PYSPARK_VERSION} glow.py dataclasses

# Set the PATH to use the virtual environment
ENV PATH="/opt/venv/bin:$PATH"

WORKDIR /
ADD Dockerfile /
