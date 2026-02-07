# image base
FROM node:20-alpine

# work dir
WORKDIR /app

# COPY the package dependencies, cache, no install if json file stays the same
COPY ./package.json /app
COPY ./package-lock.json /app

# RUN, run during the image build
RUN ["npm", "install"]

# copy the rest
COPY . .

# only one CMD per dockerfile, run after the container started
RUN ["npm", "run", "build"]

# -- means the rest of args are for vite preview, not npm
CMD ["npm", "run", "preview", "--", "--host", "0.0.0.0"]

