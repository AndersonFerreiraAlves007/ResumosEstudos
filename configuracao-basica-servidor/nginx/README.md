# Instalação do nginx:
  1. sudo apt update
  2. sudo apt install nginx
  3. ufw enable
  4. sudo ufw app list
  5. sudo ufw allow 'Nginx Full'
  6. sudo ufw delete allow 'Nginx HTTP'
  7. systemctl status nginx

# Configuração do site no nginx e configuração do proxy reverso:
  Fazer esse procedimento pra cada hostNameVaiAqui que desejar. 
  
  1. Crie um arquivo hostNameVaiAqui.conf na pasta /etc/nginx/sites-available do nginx com este conteúdo abaixo:

```
	server {
    listen 80;
    listen [::]:80;

    server_name hostNameVaiAqui;

    root /var/www/hostNameVaiAqui;
    index index.html;

    location / { # Proxy Reverso inicia aqui
      proxy_pass http://localhost:3333;
      proxy_http_version 1.1;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Connection 'upgrade';
      proxy_set_header Host $host;
      proxy_cache_bypass $http_upgrade;
    }
	}
```

  2. sudo ln -s /etc/nginx/sites-available/hostNameVaiAqui.conf /etc/nginx/sites-enabled/
  4. sudo nginx -t
  5. sudo systemctl reload nginx


# Configuração SSL com Let's Encrypt: 
  1. sudo apt install certbot python3-certbot-nginx
  
  (Fazer esse procedimento pra cada hostNameVaiAqui que desejar)

  2. sudo certbot certonly --agree-tos --email aquiVaiOEmailDaPessoa@gmail.com -d hostNameVaiAqui
  3. sudo systemctl status certbot.timer
  4. sudo certbot renew --dry-run

  5. adicionar esse snippet ao final do hostNameVaiAqui.conf já criado em /etc/nginx/sites-available)

  ```
  server {
    ... # Conteúdo anterior

    listen [::]:443 ssl;
    listen 443 ssl;
    ssl_certificate /etc/letsencrypt/live/hostNameVaiAqui/fullchain.pem; 
    ssl_certificate_key /etc/letsencrypt/live/hostNameVaiAqui/privkey.pem;
    include /etc/letsencrypt/options-ssl-nginx.conf;
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; 
  }
  ```

  6. sudo nginx -t
  7. sudo systemctl restart nginx

# Apenas para referencia de como inicar/parar o Nginx
  sudo systemctl stop nginx
  sudo systemctl start nginx
  sudo systemctl restart nginx
  sudo systemctl reload nginx