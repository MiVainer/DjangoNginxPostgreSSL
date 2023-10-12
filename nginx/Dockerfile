FROM nginx:latest

RUN rm /etc/nginx/conf.d/default.conf && rm /etc/nginx/nginx.conf
COPY conf.d/nginx.conf /etc/nginx/conf.d/
COPY ./nginx.conf /etc/nginx/
