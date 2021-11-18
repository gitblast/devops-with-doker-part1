FROM ubuntu

EXPOSE 5000

WORKDIR /usr/src/app

# install curl
RUN apt-get update && apt-get install -y curl

# install node
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash

RUN apt-get install -y nodejs

COPY . .

ENV REACT_APP_BACKEND_URL=http://localhost:8080

RUN npm install && npm run build

RUN npm install -g serve

CMD serve -s -l 5000 build