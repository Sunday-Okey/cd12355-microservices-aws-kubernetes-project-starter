FROM python:3.10-slim-buster

USER root

WORKDIR /src

COPY ./requirements.txt requirements.txt

# Install system dependencies
RUN apt update -y && apt install -y --no-install-recommends \
    build-essential libpq-dev

# Install Python dependencies first
COPY requirements.txt .
RUN pip install --upgrade pip setuptools wheel \
    && pip install -r requirements.txt

# Copy the rest of the app
COPY . .

CMD ["python", "app.py"]