# Base image
FROM ubuntu:latest
# Install Python 3 and pip
RUN apt-get update && apt-get install -y python3 python3-pip
# Install Flask using pip3
RUN pip3 install Flask
# Copy the Python script to the container
COPY api.py /app/api.py
# Set the working directory
WORKDIR /app
# Expose port 5252
EXPOSE 5252
# Set the command to be run when the container starts
CMD ["python3", "api.py"]
