# Use an official Ubuntu runtime as a parent image
FROM ubuntu:20.04

# Set the working directory in the container
WORKDIR /app

# Install required packages
RUN apt-get update && apt-get install -y \
    fortune \
    cowsay \
    netcat \
    && rm -rf /var/lib/apt/lists/*

# Ensure /usr/games is in the PATH
ENV PATH="/usr/games:${PATH}"

# Copy the contents of the wisecow directory to /app
COPY wisecow/ ./

# Make sure the script is executable
RUN chmod +x wisecow.sh

# Make port 4499 available to the world outside this container
EXPOSE 4499

# Run wisecow.sh when the container launches
CMD ["./wisecow.sh"]

