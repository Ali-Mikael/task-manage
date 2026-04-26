FROM node:latest AS dev

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

RUN chown -R node:node /app

USER node

EXPOSE 5000

CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]
