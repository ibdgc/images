# Use an official Python runtime as a parent image
FROM python:3.8-slim

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file into the container
COPY $BUILD_PATH/requirements.txt .
COPY images .
COPY ibdgc-db/ .

# Install any needed packages specified in requirements.txt
RUN pip install -r requirements.txt

# Install the current repository as a Python package
RUN pip install ibdgc-db/
