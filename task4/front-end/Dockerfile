# Base image - lastes version Nginx
FROM nginx:latest

# Copy the softy-pinko-front-end files to the Docker image
COPY ./softy-pinko-front-end /var/www/html/softy-pinko-front-end

# Copy the Nginx config file to the Docker image
COPY ./softy-pinko-front-end.conf /etc/nginx/conf.d/default.conf
