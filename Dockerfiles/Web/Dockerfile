FROM nginx:alpine
LABEL project="app-java"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginx.conf  /etc/nginx/conf.d/nginx.conf
EXPOSE 80