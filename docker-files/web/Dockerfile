# Reference: https://hub.docker.com/_/nginx
FROM nginx:latest


# Remove Nginx’s default config.
# The Docker Hub docs tell us this is at /etc/nginx/conf.d/default.conf
RUN rm /etc/nginx/conf.d/default.conf


# Copy our custom reverse proxy configuration.
COPY vprofile.conf /etc/nginx/conf.d/vprofile.conf


# Nginx listens on port 80 by default (documented on Docker Hub).
EXPOSE 80