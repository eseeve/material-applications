FROM node:14

EXPOSE 5000

WORKDIR /usr/src/app

RUN useradd -m appuser
RUN chown appuser ./

COPY package*.json ./

RUN npm install

COPY . .

ENV REACT_APP_BACKEND_URL=http://localhost:8080

RUN npm run build
RUN npm install -g serve

USER appuser
CMD ["serve", "-s", "-l", "5000", "build"]