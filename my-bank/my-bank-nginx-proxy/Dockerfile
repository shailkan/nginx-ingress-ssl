FROM nginx

RUN mkdir /etc/nginx/certificate
WORKDIR /etc/nginx/certificate
RUN printf "\n\n\n\n\n\n\n" | openssl req -new -newkey rsa:4096 -x509 -sha256 -days 365 -nodes -out nginx-certificate.crt -keyout nginx.key
COPY default.conf /etc/nginx/conf.d/default.conf
ADD index.html /usr/share/nginx/html
ADD error.html /usr/share/nginx/html

CMD nginx -g "daemon off;"