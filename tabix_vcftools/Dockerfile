# Use the official Debian Buster Backports image as the base
FROM debian:buster-backports

LABEL maintainer="Olivier Sallou <osallou@irisa.fr>" \
      version="1" \
      software="Biocontainers debian based" \
      software.version="debian-buster-backports" \
      about.home="http://biocontainers.pro" \
      about.documentation="https://github.com/BioContainers/specs/wiki" \
      license="https://github.com/BioContainers/containers/blob/master/LICENSE"

# Set non-interactive mode
ENV DEBIAN_FRONTEND=noninteractive

# Switch to root user to install system packages
USER root

# Update package lists and install vcftools
RUN apt-get update && \
    apt-get install -y vcftools && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Add user biodocker and set up directories
RUN useradd -m -s /bin/bash biodocker && \
    mkdir /home/biodocker/bin && \
    chown biodocker:biodocker /home/biodocker/bin

# Switch back to the biodocker user
USER biodocker

# Set environment variables
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/home/biodocker/bin
ENV HOME=/home/biodocker


