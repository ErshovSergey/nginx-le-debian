FROM debian:stable

RUN  apt-get update \
#    && apt-get install -y nginx openssh-server supervisor
    && apt-get install -y nginx nginx-extras certbot tzdata openssl

ADD script/entrypoint.sh /entrypoint.sh
ADD script/le.sh /le.sh

RUN \
# rm /etc/nginx/conf.d/default.conf && \
 chmod +x /entrypoint.sh && \
 chmod +x /le.sh && \
 rm -rf /var/cache/apk/*

CMD ["/entrypoint.sh"]

#RUN useradd -ms /bin/bash newuser
#RUN echo 'newuser:test' | chpasswd

#EXPOSE 22 80

#ADD supervisord.conf /etc/supervisor/supervisord.conf

#CMD ["/usr/bin/supervisord"]


#FROM nginx:1.17.8-alpine

#ADD conf/nginx.conf /etc/nginx/nginx.conf
##ADD conf/service.conf /etc/nginx/conf.d/service.conf

#ADD script/entrypoint.sh /entrypoint.sh
#ADD script/le.sh /le.sh

#RUN \
# rm /etc/nginx/conf.d/default.conf && \
# chmod +x /entrypoint.sh && \
# chmod +x /le.sh && \
# apk add  --update certbot tzdata openssl && \
# rm -rf /var/cache/apk/*

#CMD ["/entrypoint.sh"]
