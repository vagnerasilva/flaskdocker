
# Montando manualmente Flask em Docker

apt-get update
apt-get install sudo
sudo apt install python3-pip

pip3 install flask

cd app 
python3 app.py  



!!!!! Erro na instalacao do mkl-service==2.3.0


Executando depois de montado

docker container run -it --name flaskgcp1 -v $(pwd):/app -p 8080:5000 vagnerasilva/flaskgcp:1.1 /bin/bash

# baixar a imagem base para criar a imagem com o codigo
docker pull vagnerasilva/flaskgcp:1.1

# executar para alteracoes da versao 1.2 dentro da pasta do codigo
docker container run -it --name flaskgcp1 -v $(pwd):/app -p 8080:5000 vagnerasilva/flaskgcp:1.1 /bin/bash

## realizar alteracoes e gerar uma imagem nova com o container em execucao em outro terminal
docker commit <number IDcontainer> vagnerasilva/flaskgcp:1.2

# caso tenha alteracoes colocar 1.2 no dockerfile

# buildar a imagen para testes
docker build -t dev_docker_flask .

# para teste 

docker container run -it --name dev_container_flask -p 8080:5000 dev_docker_flask /bin/bash


# buildar a imagen para prod
docker build -t prod_docker_flask .

# para producao
#### para o caso do dockerfile sem CMD
docker run -d --name prod_container_flask -p 8080:5000 prod_docker_flask python3 app.py

#### para o caso do dockerfile com CMD
docker run -d --name prod_container_flask -p 8080:5000 prod_docker_flask 
