FROM node:18-alpine

WORKDIR /app

# Copy package files and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy Prisma schema folder (make sure your schema.prisma is inside ./prisma)
COPY prisma ./prisma

# Generate Prisma client inside the image
RUN npx prisma generate

# Copy the rest of your app files
COPY . .

EXPOSE 5000

CMD ["node", "./src/server.js"]
