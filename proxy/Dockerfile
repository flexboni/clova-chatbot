# Use the official image as a parent image.
FROM nginx:stable

# Maintainer
MAINTAINER t<t@test.com>

# Copy the nginx conf file
COPY nginx.conf /etc/nginx/nginx.conf

CMD ["nginx", "-g", "daemon off;"]