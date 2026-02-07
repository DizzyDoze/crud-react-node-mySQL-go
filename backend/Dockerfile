# node 20 image
FROM node:20-alpine

# root path
WORKDIR /app

# src(local) -> dest(container)
# copy packages file first, this will cache
# no npm install happens if json stay the same
COPY ./package.json /app
COPY ./package-lock.json /app

# command to run during build
RUN ["npm", "install"]

# copy the rest of the files
COPY . .

# cmd to run once container started
CMD ["npm", "start"]
