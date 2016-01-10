# sslbox

Minimal ssl enabled (via letsencrypt) webserver for secure file sharing

### setup ssl certificates

Do this on a machine that can serve content for your `example.com` domain

```
git clone https://github.com/letsencrypt/letsencrypt
cd letsencrypt
./letsencrypt-auto certonly --standalone -d example.com -d www.example.com
```

### install dependencies

```
pip install Flask
```

### run the server

```
./sslbox \
--cert /etc/letsencrypt/live/www.example.com/fullchain.pem \
--key /etc/letsencrypt/live/www.example.com/privkey.pem
```
