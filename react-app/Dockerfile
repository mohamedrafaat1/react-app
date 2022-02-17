FROM node:alpine as builder
WORKDIR '/app'
COPY package.json .0
COPY ./ ./
CMD echo '${pwd}'
RUN npm run build

FROM nginx
EXPOSE 80
COPY --from=builder /app/build /usr/share/nginx/html
