FROM node:alpine AS dave
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
CMD ["npm", "run", "build"]

FROM nginx
EXPOSE 3000
COPY --from=dave /app/build /usr/share/nginx/html
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf