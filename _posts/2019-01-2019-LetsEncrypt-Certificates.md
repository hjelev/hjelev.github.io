---
layout: post
title: Install LetsEncrypt Certificate
date: 2019-01-19
categories: linux
---

Install let’s encrypt:
  <pre>$sudo apt-get install certbot</pre>
  
Generate the certificate:
  <pre>$sudo certbot certonly --standalone -d example.com -d www.example.com</pre>

The certificate files will be located at: `/etc/letsencrypt/live/example.com`

Modify the nginx config file for example.com located in `/etc/nginx/sites-available` .


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

Check if the changes you have made to nginx configuration files are valid:
  <pre>$nginx -t</pre>

Reload Nginx Configuration:

  <pre>$sudo /etc/init.d/nginx reload</pre>

Renew your certificates:

Let's Encrypt certificates are valid for 90 days. To renew your expiring certificate(s) use the command below:

   <pre>$sudo certbot renew</pre>
