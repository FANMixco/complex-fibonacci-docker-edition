FROM node:alpine
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
#related to nodemon and volumes
CMD ["npm", "run", "start"]