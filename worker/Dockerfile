FROM node:16-alpine
WORKDIR '/app'
# or COPY package.json .
COPY ./package.json ./ 
RUN npm install
COPY . .
# npm run start is normally for prod ready version of this app, defined in packge.json 
CMD ["npm","run","start"] 