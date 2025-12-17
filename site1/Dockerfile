FROM nginx:alpine
COPY . /usr/share/nginx/html
RUN sed -i 's/80/81/g' /etc/nginx/conf.d/default.conf
EXPOSE 81
CMD ["nginx", "-g", "daemon off;"]
