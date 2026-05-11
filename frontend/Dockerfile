FROM node:20-slim AS build
WORKDIR /app

RUN npm install

COPY . .

RUN npm run build

FROM node:20-slim

COPY --from=build /app/dist /usr/share/nginx/html
