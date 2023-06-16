FROM nginx
RUN  rm -rf /usr/share/nginx/html/index.html
RUN  rm -rf /etc/nginx/ngin.conf
RUN  rm -rf /etc/nginx/conf.d/default.conf
COPY default.conf.template /etc/nginx/nginx.conf
ADD /static /usr/share/nginx/html/
EXPOSE 80
ENV CATALOGUE_HOST="catalogue"