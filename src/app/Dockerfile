# create image based on latest version
FROM node:latest AS frontend

# create main directory
WORKDIR /usr/src/app

# copy files from local folder app to container folder app
COPY . .

# install node packages
RUN yarn global add @vue/cli && yarn install

# bind mount app directory to container app
RUN --mount=type=bind,source=.,target=/usr/src/app

# expose port that app uses
EXPOSE 8080

# run vue app
CMD ["yarn", "run", "serve"]
