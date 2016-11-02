FROM nginx
 
#RUN apt-get update && apt-get install nginx nginx-extras gettext -y

#RUN rm /etc/nginx/sites-enabled/default

# use substenv to replace variables in config defined outside
COPY config/nginx.template /tmp/nginx.template
