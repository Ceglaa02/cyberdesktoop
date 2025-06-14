FROM node:24.2-alpine

COPY ./app/frontend/package*.json ./

RUN npm install
COPY ./app/frontend .

WORKDIR /app
EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host"]