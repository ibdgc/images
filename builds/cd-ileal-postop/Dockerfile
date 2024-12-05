# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Copy src code into the container
# COPY ibdgc-db/ ibdgc-db

RUN apt-get update && apt-get install \
  git \
  python3-dev \
  graphviz \
  libgraphviz-dev \
  pkg-config \
  build-essential \
  gcc \
  awscli \
  -y --no-install-recommends

# Install dataforge from GitLab
RUN pip install --upgrade pip
RUN pip install --no-cache-dir "dataforge[redcap,frictionless] @ git+https://gitlab.com/pschumm/data-forge.git@d2736266cc26c35f87a2145095c87120e1ec6395
