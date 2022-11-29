# mysite

# executar um servidor web básico usando a imagem NGINX oficial
docker run -it --rm -d -p 8080:80 --name web nginx
# Storp servidro
docker stop web

# Adiciona Html personalizado
docker run -it --rm -d -p 8080:80 --name web -v ~/site-content:/usr/share/nginx/html nginx

# Criação de uma imagem personalizada 
FROM nginx:latest
COPY ./index.html /usr/share/nginx/html/index.html

# Para construir nossa imagem
docker build -t webserver .

# criar uma montagem de ligação para incluir nosso html
docker run -it --rm -d -p 8080:80 --name web webserver