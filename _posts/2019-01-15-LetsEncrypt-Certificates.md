---
layout: post
title: Install LetsEncrypt Certificate
date: 2019-01-15
categories: linux
---
![LetsEncrypt](/static/img/letsencrypt.png)

# In this article I'll explain how I installed LetsEncrypt certificate for my home-assistant instance that is behind a nginx reverse proxy.

1. We need to install Let’s Encrypt:
   <pre>$sudo apt-get install certbot</pre>
  
2. Once LetsEncrypt is installed we have to generate the certificate:
    <pre>$sudo certbot certonly --standalone -d example.com -d www.example.com</pre>
    
    (You need to replace example.com with your domain name)

    During the generation you'll be asked for email address which LetsEncrypt will use to contact you if there are issues with the certificate.
    The certificate files will be located at: `/etc/letsencrypt/live/example.com`
    
    If you are running nginx on the same machine you'll get an error that port 80 is not available as its used for prooving that you are the domain owner. If this is the case you'll need to stop nginx during the certificate generation `$sudo /etc/init.d/nginx stop` and enable it once the generation is completed `$sudo /etc/init.d/nginx start` . 
    
    
    ![CertBot](/static/img/certbot-logo.png)
    
3. Once the certificate is generated we need to modify the nginx configuration file for that domain.
    The configuration file that we need to modify is located in `/etc/nginx/sites-available` .

    nginx config file:
    (this is the nginx configuration I have used to enable SSL for my Home-assistant setup.)

    <pre>
    map $http_upgrade $connection_upgrade {
        default upgrade;
        ''      close;
    }
    server {
    	listen 80;
    	listen 443 ssl;
        server_name example.com;
        access_log  /var/log/nginx/access.log;
    	ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
    	ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;
        location / {
            proxy_pass http://192.168.0.103:8123;
            proxy_set_header Host $host;
            proxy_redirect http:// https://;
            proxy_http_version 1.1;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection $connection_upgrade;
        }
    
    }
    </pre>

4. Check if the changes you have made to nginx configuration files are valid:
    <pre>$nginx -t</pre>

5. Reload Nginx Configuration:
    <pre>$sudo /etc/init.d/nginx reload</pre>

6. Renew your certificates:

    Let's Encrypt certificates are valid for 90 days. To renew your expiring certificate(s) use the command below:
    <pre>$sudo certbot renew</pre>
