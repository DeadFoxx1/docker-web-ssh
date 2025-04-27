# docker-web-ssh
A fun little addition to my homelab ig  

# Setup:
```sh
git clone https://github.com/DeadFoxx1/docker-web-ssh.git  
cd docker-web-ssh  
mkdir ssl  
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ssl/nginx-selfsigned.key -out ssl/nginx-selfsigned.crt  
docker compose up -d
```
