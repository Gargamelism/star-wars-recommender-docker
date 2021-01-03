FROM node:latest

RUN apt-get update && apt-get -y install git nodejs
RUN curl https://www.npmjs.com/install.sh | sh

WORKDIR /app/front

RUN git clone https://github.com/Gargamelism/star-wars-recommender-frontend.git .
RUN npm install

COPY ./docker_compose/node/start.sh /start.sh
RUN sed -i 's/\r//' /start.sh
RUN chmod +x /start.sh