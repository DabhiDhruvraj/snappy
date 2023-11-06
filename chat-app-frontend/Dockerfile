# FROM node:16-alpine
# WORKDIR /app
# COPY package.json ./
# RUN npm install babel
# RUN yarn install
# COPY . .
# EXPOSE 3000
# CMD ["yarn","start"] 

FROM node:16-alpine AS build

WORKDIR /frontend
COPY package.json package.json
RUN npm i
COPY . .
RUN npm run-script build

FROM nginx:alpine

COPY --from=build /frontend/build /var/www/html
COPY default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx","-g","daemon off;"]