#FROM nginxinc/nginx-unprivileged:stable
#COPY build /usr/share/nginx/html

FROM ubuntu
RUN apt-get update
RUN apt-get install nginx -y
COPY build /var/www/html/
COPY config.sh .
EXPOSE 80
RUN ["chmod", "+x", "./config.sh"]
ENTRYPOINT ["sh", "config.sh"]