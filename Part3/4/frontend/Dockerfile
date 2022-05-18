FROM ubuntu:18.04

EXPOSE 5000

WORKDIR /usr/src/app

COPY package*.json .

COPY . .

RUN apt-get update &&\
apt-get install curl -y &&\
curl -fssL https://deb.nodesource.com/setup_16.x | bash &&\
apt install nodejs -y &&\
npm install &&\
REACT_APP_BACKEND_URL=http://localhost:8080 npm run build &&\
npm install -g serve &&\
apt-get purge -y --auto-remove curl &&\
rm -rf /var/lib/apt/lists/* &&\
useradd -m reguser

USER reguser

CMD ["serve","-s", "-l", "5000", "build"]