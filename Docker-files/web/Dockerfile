#web dockerfile
FROM nginx
LABEL "project"="vprofile"
LABEL "Author"="Aamir"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf

