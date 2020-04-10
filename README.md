# GoPhish

## Generate SSL Certificates using Let's Encrypt
- Shell into the Nginx container:
    - `docker exec -it gophish-proxy bash`
- Run Certbot:
    - `certbot --nginx`
- Follow on-screen prompt