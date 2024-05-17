# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file into the container
COPY requirements.txt .
COPY ibdgc-db/ ibdgc-db

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

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Install the current repository as a Python package
RUN pip install --no-cache-dir ibdgc-db/
