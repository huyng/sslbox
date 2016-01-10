# sslbox

SSLBox is a minimal ssl-enabled webserver for secure file sharing.

### setup ssl certificates

Do this on a machine that can serve content for your `example.com` domain

```
git clone https://github.com/letsencrypt/letsencrypt
cd letsencrypt
./letsencrypt-auto certonly --standalone -d example.com -d www.example.com
```

This will create certificates for your server and store them in the following folder

```
/etc/letsencrypt/live/www.example.com/
```

### install dependencies

```
pip install Flask
```

### run the server

```
sudo ./sslbox \
--cert /etc/letsencrypt/live/www.example.com/fullchain.pem \
--key /etc/letsencrypt/live/www.example.com/privkey.pem \
--upload_folder ./secure_user_uploads
```
