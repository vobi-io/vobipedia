## Proxy and SSL for pm2 process

```cd /etc/nginx/sites-available/```
```nano example.conf```

```
server {
  server_name  api.example.com;
  listen 80;
  location / {
      proxy_pass http://localhost:8002;
      proxy_http_version 1.1;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Connection 'upgrade';
      proxy_set_header Host $host;
      proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
      proxy_set_header X-Forwarded-Proto $scheme;
      proxy_cache_bypass $http_upgrade;
  }
}
```
Copy config to /sites-enabled folder

``` sudo ln -s /etc/nginx/sites-available/example.conf /etc/nginx/sites-enabled/example.conf ```

Restart nginx
``` sudo service nginx restart ```


### Isntall certbot from https://certbot.eff.org/

```sudo apt-get install software-properties-common
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install python-certbot-nginx
sudo certbot --nginx

