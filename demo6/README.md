## Step 1 – Installing Nginx

```
sudo apt update
sudo apt install nginx
```

## Step 2 – Setting Up Server Blocks

    2.1 sudo mkdir -p /var/www/techdevops.ml/html

    2.2 sudo chown -R $USER:$USER /var/www/techdevops.ml/html

    2.3 sudo chmod -R 755 /var/www/techdevops.ml

    2.4 vim /var/www/techdevops.ml/html/index.html

    <html>
        <head>
            <title>Welcome to techdevops.ml!</title>
        </head>
        <body>
            <h1>Success!  The techdevops.ml server is working!</h1>
        </body>
    </html>

    2.5 sudo nano /etc/nginx/sites-available/techdevops.ml

    server {
            listen 80;
            listen [::]:80;

            root /var/www/techdevops.ml/html;
            index index.html index.htm index.nginx-debian.html;

            server_name techdevops.ml www.techdevops.ml;

            location / {
                    try_files $uri $uri/ =404;
            }
    }

    2.6 sudo ln -s /etc/nginx/sites-available/techdevops.ml /etc/nginx/sites-enabled/

    2.7 sudo nginx -t

    2.8 sudo systemctl restart nginx

    2.9 http://techdevops.ml


## Step 3 — Installing Certbot
```
sudo apt install certbot python3-certbot-nginx
```
## Step 4 — Obtaining an SSL Certificate
```
sudo certbot --nginx -d techdevops.ml -d www.techdevops.ml
```

## Step 5 — Verifying Certbot Auto-Renewal

Let’s Encrypt’s certificates are only valid for ninety days. This is to encourage users to automate their certificate renewal process. The certbot package we installed takes care of this for us by adding a systemd timer that will run twice a day and automatically renew any certificate that’s within thirty days of expiration.

```
sudo systemctl status certbot.timer

sudo certbot renew --dry-run
```





