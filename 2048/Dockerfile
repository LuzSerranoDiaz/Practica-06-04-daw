FROM nginx

WORKDIR /usr/share/nginx/html/

RUN apt update \
    && apt install git -y \
    && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/josejuansanchez/2048 /app \
    && cp -R /app/* /usr/share/nginx/html/ \
    && rm -rf /app

#No necesario 

EXPOSE 80

# ENTRYPOINT ["entrypoint.sh"]

CMD ["nginx", "-g", "daemon off;"]