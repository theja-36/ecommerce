FROM node:20-alpine

WORKDIR /app

COPY . .

RUN npm ci

RUN npm run build -- --filter=@dtc/backend

WORKDIR /app/apps/backend

EXPOSE 9000

CMD ["npm", "run", "start"]