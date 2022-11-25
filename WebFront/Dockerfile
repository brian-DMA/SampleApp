FROM node:latest as build
WORKDIR /WebFront
COPY . .
RUN npm install -g @angular/cli
RUN npm install
RUN ng build

FROM nginx:latest as deploy
WORKDIR /WebFront
COPY --from=build /WebFront/dist/sampleapp/*.* /usr/share/nginx/html/
