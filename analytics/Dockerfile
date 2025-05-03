FROM python:3.10-slim-buster

WORKDIR /app

# Copy the files into the container
COPY . .

RUN apt update -y && apt install build-essential libpq-dev -y
RUN pip install --upgrade pip setuptools wheel
RUN pip install -r requirements.txt


ENV DB_USERNAME=myuser
ENV DB_PASSWORD=mypassword
ENV DB_HOST=127.0.0.1
ENV DB_PORT=5433
ENV DB_NAME=mydatabase

# Set the command to run the script
CMD ["python", "app.py"]