#get linux copy
FROM node:alpine as builder

WORKDIR '/app'

#copy json file first
COPY ./package.json ./

#install dependencies
RUN npm install

#copy all repos (source code)
COPY . .

RUN npm run build

#app/build <--- final folder

#start new phase -- run
FROM nginx
EXPOSE 3000
#copy from a different stage
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html