# Base the image on the built-in Azure Functions Python image
FROM mcr.microsoft.com/azure-functions/python:4-python3.11

# Add files from this repo to the root site folder.
COPY . /home/site/wwwroot

# Install requirements
RUN cd /home/site/wwwroot && pip install -r requirements.txt