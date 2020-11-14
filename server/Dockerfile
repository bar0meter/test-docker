FROM node:12-stretch as base

ENV NODE_ENV=production

WORKDIR /node

COPY package.json package-lock*.json ./

RUN npm install --only=production && npm cache clean --force

ENV PATH /node/node_modules/.bin:$PATH

# dev enviorment
FROM base as dev

ENV NODE_ENV=development

RUN npm install --only=development

CMD ["nodemon", "./app/src/app.js"]