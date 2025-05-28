# 1) Base image olarak Node 20-alpine alıyoruz
FROM node:20-alpine

# 2) Çalışma dizini
WORKDIR /app

# 3) package.json ve lock dosyasını kopyala, bağımlılıkları yükle
COPY package*.json ./
RUN npm ci

# 4) Kaynak kodu kopyala ve build et
COPY . .
RUN npm run build

# 5) Container ayağa kalkınca dist/index.js'i çalıştır
CMD ["node", "dist/index.js"]
