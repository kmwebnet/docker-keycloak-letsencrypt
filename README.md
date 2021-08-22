# Keycloak Docker setup with NGINX Proxy and Letsencrypt
A simple Keycloak setup using NGINX Reverse Proxy and Letsencrypt.   
It's useful for serve keycloak with SSL and default port 443.  
  
# Reference  
NGINX Proxy Docker image: https://github.com/jwilder/nginx-proxy  
Letsencrypt NGINX Docker Companion: https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion  
# Guide
Copy sample.env to .env and adjust the environment variables. Then docker-compose up  

Note: ssl option in JDBC_PARAMS is set to false, as the nginx proxy will handle SSL.  

```
DB_DATABASE=keycloak_db
DB_USER=keycloak_db_user
DB_PASSWORD=Passw0rd!
KEYCLOAK_HOSTNAME=example.com
KEYCLOAK_HTTP_PORT=8080
KEYCLOAK_USER=admin
KEYCLOAK_PASSWORD=Passw0rd!
JDBC_PARAMS="ssl=false" 
VIRTUAL_HOST=example.com
VIRTUAL_PORT=8080
PROXY_ADDRESS_FORWARDING=true
LETSENCRYPT_HOST=example.com
LETSENCRYPT_EMAIL=test@example.com
```

After setup, you can access your URL with SSL.  
You can use admin ID/Pass with KEYCLOAK_USER/KEYCLOAK_PASSWORD variables.   
