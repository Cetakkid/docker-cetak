# Pull nginx base image
FROM nginx:1.17.2-alpine

# running nginx and copy to workdir
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d
