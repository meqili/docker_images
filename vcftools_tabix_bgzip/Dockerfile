FROM ubuntu:18.04

LABEL maintainer="Qi Li (liq3@chop.edu)"

# Install required packages
RUN apt-get update -y && \
    apt-get install -y \
    vcftools \
    tabix \
    pigz

# Clean up apt cache to reduce image size
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set default working directory
WORKDIR /usr/src/app

# Entry point (optional)
# CMD ["/bin/bash"]

