### Build stage
FROM node:18-alpine AS build
WORKDIR /app

# install deps
COPY package*.json ./
RUN npm install

# copy sources and build
COPY . .
RUN npm run build

### Production stage
FROM nginx:stable-alpine
COPY --from=build /app/build /usr/share/nginx/html

# remove default nginx conf if present and use default behavior
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
