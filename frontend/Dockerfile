FROM node:alphine As a builder
WORKDIR /app
RUN npm install --legacy-peer-deps
RUN npm run build
COPY . .
#stage-2
FROM Node:alphine as a production
WORKDIR /app
