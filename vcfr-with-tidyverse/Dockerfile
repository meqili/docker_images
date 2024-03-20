# Use Ubuntu 22.04 as the base image
FROM ubuntu:22.04

# Set the maintainer label
LABEL maintainer="Qi Li (liq3@email.chop.edu)"

# Set non-interactive mode for Debian packages installation
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=America/New_York

# Update package lists and install necessary dependencies
RUN apt-get update && \
    apt-get install -y gnupg2 && \
    apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9 && \
    echo "deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/" >> /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y make libssl-dev libfreetype6-dev libfribidi-dev libharfbuzz-dev pandoc zlib1g-dev libxml2-dev libicu-dev libcurl4-openssl-dev libfontconfig1-dev libjpeg-dev libpng-dev libtiff-dev r-base

# Verify R installation and version
RUN R -e "install.packages(c('tidyverse', 'vcfR'))"

# Set the working directory
WORKDIR /

# Define the command to be run when the container starts
CMD ["bash"]

