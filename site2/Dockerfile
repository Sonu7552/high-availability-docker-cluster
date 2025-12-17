FROM nginx:alpine
COPY . /usr/share/nginx/html
RUN sed -i 's/80/82/g' /etc/nginx/conf.d/default.conf
EXPOSE 82
CMD ["nginx", "-g", "daemon off;"]
