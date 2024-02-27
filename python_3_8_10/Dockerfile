# Use the Ubuntu 20.04 base image
FROM ubuntu:20.04

# Set the maintainer label
LABEL maintainer="Qi Li (liq3@email.chop.edu)"

# Set non-interactive mode for Debian packages installation
ENV DEBIAN_FRONTEND=noninteractive

# Update the package list and install necessary packages
RUN apt-get update && \
    apt-get install -y python-is-python3 python3-pip default-jre && \
    pip install numpy pandas && \
    apt-get autoremove -y && \
    apt-get autoclean -y

# Set the working directory
WORKDIR /

# Copy the Dockerfile into the container (not typically needed during the build process)
COPY Dockerfile /

# Define the command to be run when the container starts
CMD ["bash"]

