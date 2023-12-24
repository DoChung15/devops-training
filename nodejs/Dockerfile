FROM node:16-alpine

ARG BUILD_ENV=${BUILD_ENV}

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

COPY .env.${BUILD_ENV:-dev} ./.env

EXPOSE 3000

# Define environment variables
ENV MYSQL_HOST=db
ENV MYSQL_USER=training
ENV MYSQL_PASSWORD=training_pw
ENV MYSQL_DATABASE=user

CMD ["node", "app.js"]
