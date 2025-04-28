# docker-web-ssh
A fun little addition to my homelab ig  
I wanted to be able to ssh into my raspberry pi using my phone so I did this!   
I looked at guacamole at first but the official image isn't supported for arm64 :(  
(I know there are alternatives but I only wanted ssh anyways so) 

# About:
A docker network with:   
wetty as the terminal,  
openssh for the ssh server,  
and a reverse proxy using nginx  

Nginx is open on port 443 and the ssh client can be accessed using https://hostname/ssh  
(in my case it was https://raspi.local/ssh because thats what my server's hostname was)  
the user is Dfox (because that meeeee)  
and the password is just password  
(both username and password can be easily changed in the docker file btw)  

# Sources:
I based this project on the following sources:  
[how-to-set-up-web-based-ssh](https://linuxiac.com/how-to-set-up-web-based-ssh/)(they use caddy instead of nginx)  
[how-to-create-a-self-signed-ssl-certificate-for-nginx-in-ubuntu-20-04-1](https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-nginx-in-ubuntu-20-04-1)  
[reverse-proxy-nginx-docker-compose](https://weberdominik.com/blog/reverse-proxy-nginx-docker-compose)  
as well as countless stack overflow threads  
I'm just experimenting here so please check them out they were a huuuuge help

# Setup:
```sh
git clone https://github.com/DeadFoxx1/docker-web-ssh.git  
cd docker-web-ssh
```
I didn't feel like figuring out ssl with letsencrypt or somthing so I opted for self signed:  
(these will be expected by the docker compose file)
```sh
mkdir ssl  
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ssl/nginx-selfsigned.key -out ssl/nginx-selfsigned.crt
```
# Run it :3
```sh
docker compose up -d
```
