# DokerMarhaba


FROM node:16

WORKDIR /app

COPY package.json .

RUN npm install

COPY . ./

EXPOSE 80

CMD ["npm", "start"]

​

Créer un network, et lui donner le nom de hotel-booking-net

​

docker network create hotel-booking-net.

​

executez un container basé sur l'image mongo, nommez-le hotel-booking-db et faites-le utiliser avec le network hotel-booking-net.

​

docker container run -d --name hotel-booking-db -v hotel-booking-db:/data/db --network hotel-booking-net mongo

​

Entrer dans le dossier du serveur ou se trouver Dockerfile et creer cette image et nommez-la hotel-booking-docker:test

​

docker build -t livraison-marhaba-image .

​

exécutez un container basé sur cette image que vous venez de créer, nommez-le hotel-booking et faites-le utiliser avec le network hotel-booking-net.

​

docker container run -d --name livraison-marhaba-frontend -v ${pwd}:/app -v /app/node_modules --network livraison-marhaba-net -p 3000:3000 livraison-marhaba-frontend:test
