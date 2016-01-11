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

### screenshots

<img width="743" alt="screen shot 2016-01-10 at 6 21 55 pm" src="https://cloud.githubusercontent.com/assets/121183/12225813/542961c4-b7c7-11e5-8b65-b889116c6fa1.png">

