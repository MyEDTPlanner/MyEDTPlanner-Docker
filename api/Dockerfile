FROM node:18-alpine AS build
WORKDIR /app

RUN apk update && apk add curl && apk add unzip
RUN curl --location --output master.zip https://github.com/MyEDTPlanner/MyEDTPlanner-API/archive/master.zip
RUN unzip master.zip
RUN rm master.zip
RUN mv MyEDTPlanner-API-main/* .
RUN npm install
COPY . .
RUN npm install
# Définir les variables d'environnement pour l'application
 
# Exposer le port sur lequel l'application s'exécute
CMD [ "node","app.js" ]
EXPOSE 2000
