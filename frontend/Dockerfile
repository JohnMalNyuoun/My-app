FROM node:20-alpine

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm ci

COPY . .

ARG VITE_BACKEND_URL
ENV VITE_BACKEND_URL=${VITE_BACKEND_URL}

RUN npm test
RUN npm run build
RUN npm install --global serve

EXPOSE 5173

CMD ["serve", "-s", "dist", "-l", "5173"]
