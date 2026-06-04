FROM node:18.0.0-alpine

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY . .
ENV NODE_OPTIONS=--openssl-legacy-provider

ARG API_KEY
ENV TMDB_KEY=${API_KEY}

RUN npm install

RUN npm run build

RUN npm install -g serve

EXPOSE 5173

CMD ["serve","-s","dist","-l","5173"]
