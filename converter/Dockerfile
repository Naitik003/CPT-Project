# Use the official Python 3.10 image with a slim Debian Bullseye base
FROM python:3.10-slim-bullseye
# Update package information and install required dependencies
RUN apt-get update \
  && apt-get install -y --no-install-recommends --no-install-suggests \
  build-essential ffmpeg \
  && pip install --no-cache-dir --upgrade pip
# Set the working directory to /app
WORKDIR /app
# Copy the requirements.txt file to the working directory
COPY ./requirements.txt /app
# Install Python dependencies from requirements.txt
RUN pip install --no-cache-dir --requirement /app/requirements.txt
# Copy the current directory contents into the container at /app
COPY . /app
# Set the default command to run when the container starts
CMD ["python3", "consumer.py"]
