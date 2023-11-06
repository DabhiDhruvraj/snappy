FROM node:16-alpine
WORKDIR /app
COPY package*.json ./
RUN yarn global add nodemon
RUN yarn install
COPY . .
EXPOSE 5000
CMD ["nodemon","index.js"]