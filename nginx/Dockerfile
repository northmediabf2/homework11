#Используем образ из Docker Hub
FROM ubuntu:16.04 
#Ставим пакеты                                                                                                    
RUN apt-get update -y && apt-get upgrade -y \                           
 && apt-get install nginx wget openssl apt-transport-https curl -y \
 && apt-get clean -y
RUN echo "daemon off;" >> /etc/nginx/nginx.conf # настраиваем nginx. определяет, должен ли nginx стать демоном.
EXPOSE 80
CMD [ "nginx" ]
