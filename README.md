# GoPhish for Production

## Features
- Docker
- Let's Encrypt
- Launch on Ubuntu 18.04 LTS Server

## Setup locally
- Build containers
    -  `make build`
- Run GoPhish
    - `make up`
- GoPhish is running on `localhost` & `localhost:3333`

## Setup on a Production Server

### Initial Setup
- Change the `server_name` in `etc/nginx/config.conf` from `127.0.0.1` to **your domain name**
- Install **Make**
    - `sudo apt install make`

### Run GoPhish on a Production Server
- Install and update required packages
    - `make init`
- Restart Server in order for changes to take effect
- Build containers
    - `make build`
- Run GoPhish
    - `make up`

#### Generate SSL Certificates using Let's Encrypt
- Shell into the Nginx container:
    - `docker exec -it gophish-proxy bash`
- Run Certbot:
    - `certbot --nginx`
- Follow on-screen prompts
- Restart Nginx service
    - `service nginx restart`
    - **Note:** the shell will close because this command restarts the container
- Restart the Nginx container
    - `make up`
- Visit your domain to access the GoPhish admin UI