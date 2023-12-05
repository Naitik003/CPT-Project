# Use the official Python 3.10 image with a slim Debian Bullseye base
FROM python:3.10-slim-bullseye
# Update package list and install essential packages for building
RUN apt-get update \
  && apt-get install -y --no-install-recommends --no-install-suggests \
  build-essential default-libmysqlclient-dev \
  && pip install --no-cache-dir --upgrade pip
# Set the working directory inside the container to /app
WORKDIR /app
# Copy the requirements.txt file to the container at /app
COPY ./requirements.txt /app
# Install Python dependencies from requirements.txt
RUN pip install --no-cache-dir --requirement /app/requirements.txt
# Copy the current directory contents into the container at /app
COPY . /app
# Expose port 5000 for the application to listen on
EXPOSE 5000
# Command to run the application when the container starts
CMD ["python3", "server.py"]

