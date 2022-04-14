FROM node:16.14-alpine

# This Dockerfile takes as context the root of the application
# i.e. execute `docker build -f src/server/Dockerfile . [...]` from the
# project's root, not this directory

RUN mkdir /app && chown node:node /app
COPY --chown=node:node . /app
WORKDIR /app

USER node
RUN yarn install --immutable

ARG PORT
EXPOSE $PORT
ENV PORT=$PORT

CMD [ "sh", "-c", "yarn start" ]
