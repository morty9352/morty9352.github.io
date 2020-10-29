# Let's Encrypt Standalone on Centos 7

1. sudo yum --enablerepo=extras install epel-release
2. sudo yum install certbot
3. certbot --version
4. sudo certbot certonly --standalone --preferred-challenges http -d example.com

## Auto-Renewal

1. sudo systemctl enable --now certbot-renew.timer
2. sudo systemctl status certbot-renew.timer

## Renew Hook

1. sudo vi /etc/letsencrypt/renewal/example.com.conf
2. renew_hook = systemctl reload rabbitmq - This goes on the last line.
3. sudo certbot renew --dry-run

