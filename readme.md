docker container run -it --name liftibm -v $(pwd):/home -p 33001:33001 vagnerasilva/ibmaction:1.0 /bin/bash
docker container run -it --name flaskgcp -v $(pwd):/app -p 5000:5000 ubuntu:18.04 /bin/bash
docker container run -it --name flaskgcp -v $(pwd):/app -p 5000:5000 vagnerasilva/flaskgcp:1.0 /bin/bash
Montando manualmente

apt-get update
apt-get install sudo
sudo apt install python3-pip

pip3 install flask

cd app 
python3 app.py  



!!!!! Erro na instalacao do mkl-service==2.3.0


Executando depois de montado

docker container run -it --name flaskgcp1 -v $(pwd):/app -p 5000:5000 vagnerasilva/flaskgcp:1.0 /bin/bash