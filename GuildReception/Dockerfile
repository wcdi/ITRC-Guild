FROM node:13.3-alpine

WORKDIR /usr/src/app
COPY package.json ./
COPY yarn.lock ./
RUN yarn install
RUN yarn build
RUN yarn generate
ENV HOST 0.0.0.0
EXPOSE 3000
 
CMD [ "yarn", "start" ]
