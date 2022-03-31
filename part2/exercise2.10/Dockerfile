FROM node:16.14.0

EXPOSE 5001

WORKDIR /usr/src/app

COPY . .

RUN npm install

RUN npm install -g serve

RUN REACT_APP_BACKEND_URL=api npm run build

CMD [ "serve", "-s", "-l", "5001", "build" ]