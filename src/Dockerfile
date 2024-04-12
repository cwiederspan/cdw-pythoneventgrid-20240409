# Base the image on the built-in Azure Functions Python image
FROM mcr.microsoft.com/azure-functions/python:4-python3.11

WORKDIR /home/site/wwwroot
COPY ./requirements.txt .
RUN pip install -r requirements.txt

COPY ./host.json .
COPY ./function_app.py .