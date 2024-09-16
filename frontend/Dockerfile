# Stage 1

FROM node as build

WORKDIR /home/app

COPY package*.json .

RUN npm install

COPY . .

RUN npm run build

# Stage 2

FROM nginx

COPY --from=build /home/app/dist /usr/share/nginx/html

ENTRYPOINT ["nginx", "-g", "daemon off;"]

