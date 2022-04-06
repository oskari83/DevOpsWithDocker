FROM node:16.14.2-alpine3.15 as build-stage

WORKDIR /usr/src/app

COPY . .

RUN npm install && \
    REACT_APP_BACKEND_URL=http://127.0.0.1:8080 npm run build

FROM node:16.14.2-alpine3.15

COPY --from=build-stage /usr/src/app/build ./usr/src/app/build
COPY --from=build-stage /usr/src/app/node_modules ./usr/src/app/node_modules
COPY --from=build-stage /usr/src/app/package.json ./usr/src/app
COPY --from=build-stage /usr/src/app/package-lock.json ./usr/src/app

WORKDIR /usr/src/app

EXPOSE 5002

RUN npm install -g serve

RUN adduser -D appuser
USER appuser

CMD [ "serve", "-s", "-l", "5002", "build" ]