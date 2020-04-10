# GoPhish

## Initial Setup
- Change the `server_name` in `etc/nginx/config.conf` from `127.0.0.1` to **your domain name**

## Generate SSL Certificates using Let's Encrypt
- Shell into the Nginx container:
    - `docker exec -it gophish-proxy bash`
- Run Certbot:
    - `certbot --nginx`
- Follow on-screen prompts