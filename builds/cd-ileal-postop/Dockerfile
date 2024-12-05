# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Copy project contents into the container
# COPY ibdgc-db/ ibdgc-db
# Before building:
#     git clone git@github.com:ibdgc/cd-ileal-postop.git
#     cd cd-ileal-postop
#     dvc fetch
#     dvc checkout
COPY cd-ileal-postop/ cd-ileal-postop

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
RUN pip install --no-cache-dir "dataforge[redcap,frictionless] @ git+https://gitlab.com/pschumm/data-forge.git@45bf034c9fc2fee9161cc87f3d42deb3d30e4375"
