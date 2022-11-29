# mysite


docker run -it --rm -d -p 8080:80 --name web nginx
docker stop web
cria 
# Copia 
FROM nginx:latest
COPY ./index.html /usr/share/nginx/html/index.html