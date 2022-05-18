FROM node:16-alpine

EXPOSE 5000

WORKDIR /usr/src/app

COPY package*.json .

COPY . .

RUN npm install
RUN REACT_APP_BACKEND_URL=http://localhost:8080 npm run build
RUN npm install -g serve
RUN adduser -D reguser

USER reguser

CMD ["serve","-s", "-l", "5000", "build"]