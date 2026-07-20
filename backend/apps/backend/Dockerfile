FROM node:20-alpine AS builder

WORKDIR /app

COPY package*.json ./
COPY turbo.json ./
COPY apps ./apps

RUN npm ci

RUN npm run build --workspace=@dtc/backend

FROM node:20-alpine

WORKDIR /app

ENV NODE_ENV=production

COPY --from=builder /app .

WORKDIR /app/apps/backend

EXPOSE 9000

CMD ["npm", "start"]