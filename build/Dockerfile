FROM nginx:alpine

# nginx
WORKDIR /etc/nginx

# www
COPY www/ /usr/share/nginx/html
RUN find /usr/share/nginx/html/ -type d -exec chmod 750 {} \; && \
    find /usr/share/nginx/html/ -type f -exec chmod 640 {} \; && \
    chown -R nginx:nginx /usr/share/nginx/html

RUN mkdir -p /var/cache/nginx /var/log/nginx \
    && chown -R nginx:nginx /var/cache/nginx /var/log/nginx /usr/share/nginx/html

EXPOSE "${NGINX_PORT}"

USER nginx

CMD ["nginx", "-g", "daemon off;"]