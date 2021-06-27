FROM alpine:3.7

RUN apk add --update nginx && rm -rf /var/cache/apk/*
#COPY files/default.conf /etc/nginx/conf.d/default.conf
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d/default.conf
#create dir for pid file
RUN mkdir -p /run/nginx
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log
CMD ["nginx", "-g", "daemon off;"]
EXPOSE 80


#FROM nginx
#RUN rm /etc/nginx/conf.d/default.conf
#RUN apt update
#RUN apt install iputils-ping -y
#COPY nginx.conf /etc/nginx/conf.d/default.conf