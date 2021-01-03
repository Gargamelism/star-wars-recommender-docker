FROM python:3

ENV PYTHONUNBUFFERED 1

# Setup Debian linux
RUN export DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get -y install build-essential curl git 

RUN mkdir app
RUN git clone https://github.com/Gargamelism/star-wars-recommender-backend.git ./app/back
WORKDIR /app/back

RUN pip install -r /app/back/requirements/requirements.txt 

COPY ./docker_compose/django/start.sh /start.sh
RUN sed -i 's/\r//' /start.sh \
    && chmod +x /start.sh