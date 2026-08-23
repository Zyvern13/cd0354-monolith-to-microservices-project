### Build
FROM beevelop/ionic:latest AS ionic
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm ci
COPY . .
RUN ionic build
### Run
FROM nginx:alpine
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=ionic /usr/src/app/www /usr/share/nginx/html
