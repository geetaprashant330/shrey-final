FROM node:18

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

RUN apt-get update && apt-get install -y python3 python3-pip
RUN pip3 install yt-dlp

EXPOSE 3000

CMD ["node", "server.js"]
