FROM debian:bullseye

EXPOSE 443

RUN apt update && apt upgrade -y
RUN apt install -y nginx openssl

RUN mkdir -p /etc/nginx/ssl /var/run/nginx /var/www/html
RUN openssl req -x509 -nodes \
	-out /etc/nginx/ssl/inception.crt \
	-keyout /etc/nginx/ssl/inception.key \
	-subj "/C=TR/L=ISANBUL/O=42Istanbul/OU=CANI_SIKILANLAR_BIRUSU/CN=maltun.42.fr/UID=maltun"

COPY conf/nginx.conf /etc/nginx/nginx.conf

CMD ["nginx", "-g", "daemon off;"]