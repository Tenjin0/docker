FROM ubuntu:latest
RUN apt-get update && \
    apt-get install -y --force-yes \
    nginx \
    vim \
    curl
RUN rm /etc/nginx/nginx.conf
COPY nginx.conf /etc/nginx/nginx.conf
RUN ln -s /etc/nginx/nginx.conf /etc/nginx/sites-available/
RUN ln -s /etc/nginx/nginx.conf /etc/nginx/sites-enabled/
RUN rm /etc/nginx/sites-enabled/default

RUN rm /etc/nginx/sites-available/default
EXPOSE 80
WORKDIR /etc/nginx
ADD start_script.sh .
RUN chmod 777 ./start_script.sh
CMD ./start_script.sh
