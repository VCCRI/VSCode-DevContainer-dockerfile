# Use an official image as a parent image
FROM ubuntu:20.04

# Install any dependencies
RUN apt-get update && apt-get install -y \
    curl \
    git \
    vim \
    R \
    libcurl4-openssl-dev
# Set the working directory
# WORKDIR /workspace