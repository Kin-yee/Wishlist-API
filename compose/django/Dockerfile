FROM python:3.8.1-buster

LABEL description = "Wishlist API"
LABEL maintainer = "rinesh.ramadhin@gmail.com"

ENV PYTHONUNBUFFERED 1

ARG POSTGRES_USER
ARG POSTGRES_DB

RUN apt-get update
RUN apt-get install ffmpeg postgresql-client -y

RUN mkdir /code

WORKDIR /code

COPY requirements.txt .

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

COPY . .

ENTRYPOINT ["./compose/services-check.sh"]
