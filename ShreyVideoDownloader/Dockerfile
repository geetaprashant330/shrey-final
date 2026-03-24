FROM node:18

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    ffmpeg

RUN pip3 install --break-system-packages yt-dlp

EXPOSE 3000

CMD ["node", "server.js"]
