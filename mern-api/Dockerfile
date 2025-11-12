FROM node:18-alpine

# set working directory
WORKDIR /app

# install dependencies
COPY package*.json ./
RUN npm install --production

# copy app
COPY . .

# make sure images dir exists for uploaded files
RUN mkdir -p /app/images

ENV PORT=4000
EXPOSE 4000

# use node directly (production)
CMD ["node", "index.js"]
