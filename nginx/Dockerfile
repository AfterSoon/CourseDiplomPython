FROM nginx:latest

RUN mkdir -p /app/static

RUN echo "server { listen 80; }" > /etc/nginx/prod.conf


COPY ./static/ /app/static/


EXPOSE 80



