# HA-proxy (notes)

## Cert Renewal
```
$ sudo mkdir /etc/ssl/xip.io
$ sudo openssl genrsa -out /etc/ssl/xip.io/xip.io.key 1024
$ sudo openssl req -new -key /etc/ssl/xip.io/xip.io.key \
                   -out /etc/ssl/xip.io/xip.io.csr
> Country Name (2 letter code) [AU]:US
> State or Province Name (full name) [Some-State]:Connecticut
> Locality Name (eg, city) []:New Haven
> Organization Name (eg, company) [Internet Widgits Pty Ltd]:SFH
> Organizational Unit Name (eg, section) []:
> Common Name (e.g. server FQDN or YOUR name) []:*.xip.io
> Email Address []:

> Please enter the following 'extra' attributes to be sent with your certificate request
> A challenge password []:
> An optional company name []:
$ sudo openssl x509 -req -days 365 -in /etc/ssl/xip.io/xip.io.csr \
                    -signkey /etc/ssl/xip.io/xip.io.key \
                    -out /etc/ssl/xip.io/xip.io.crt
```
new .pem file
```
$ sudo cat /etc/ssl/xip.io/xip.io.crt /etc/ssl/xip.io/xip.io.key \
           | sudo tee /etc/ssl/xip.io/xip.io.pem
```

#### extras
vim /etc/haproxy/haproxy.cfg

1. changes to point to new .pem file
2. restart?
```
frontend localhost
    bind *:80
    bind *:443 ssl crt /etc/ssl/xip.io/xip.io.pem
    mode http
    default_backend nodes
 ```
