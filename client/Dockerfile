FROM node:16-alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
# build this file for prod deployment
RUN npm run build

FROM nginx
EXPOSE 3000
# update our configuration file
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
# upload built files to nginx file folders
COPY --from=builder /app/build /usr/share/nginx/html