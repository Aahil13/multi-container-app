# syntax=docker/dockerfile:1

# Comments are provided throughout this file to help you get started.
# If you need more help, visit the Dockerfile reference guide at
# https://docs.docker.com/engine/reference/builder/

ARG NODE_VERSION=19.5.0

FROM node:${NODE_VERSION}-alpine

# Use production node environment by default.
ENV NODE_ENV production

WORKDIR /usr/src/app

# install nodemon for hot-reloading
RUN npm install -g nodemon

# Copy the rest of the source files into the image.
COPY . .

# Run the application as a non-root user.
RUN  chown -R node /usr/src/app
USER node

# Expose the port that the application listens on.
EXPOSE 3000

# Run the application in dev mode to use with Compose watch feature
CMD npm run dev
