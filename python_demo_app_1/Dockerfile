FROM python:3-slim

# set the working directory in the image
WORKDIR /app

# copy the files from host file system to the image file system
COPY . .

# install the necessary packages
RUN pip install flask

# set environment variable
ENV NAME=World

# Run a command to start the application
CMD ["python3", "app.py"]

