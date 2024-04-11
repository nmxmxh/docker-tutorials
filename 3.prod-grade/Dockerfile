FROM node:alpine as builder
WORKDIR '/app'
COPY package.json .
RUN yarn
COPY . . 
RUN yarn build

FROM nginx as runner
EXPOSE 80
# communiciation between developers, port mapping 
COPY --from=builder /app/build /usr/share/nginx/html