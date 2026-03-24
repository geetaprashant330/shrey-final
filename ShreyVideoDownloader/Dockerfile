FROM node:18

WORKDIR /app

COPY package*.json requirements.txt ./
RUN npm install

COPY . .

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    ffmpeg \
    && rm -rf /var/lib/apt/lists/*

# Same interpreter as runtime `python3` / `yt-dlp` shebang (avoids pip vs python mismatch)
RUN python3 -m pip install --break-system-packages --no-cache-dir -U -r requirements.txt \
    && python3 -c "import yt_dlp"

EXPOSE 3000

CMD ["node", "server.js"]
