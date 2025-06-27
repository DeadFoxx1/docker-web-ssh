# My homelab!
See the [wiki](https://github.com/DeadFoxx1/home-lab-ig/wiki) (out of date :p) for details :3  

# Setup:
```sh
git clone https://github.com/DeadFoxx1/home-lab-ig.git  
cd home-lab-ig
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
