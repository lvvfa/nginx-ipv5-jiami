# nginx-ipv6-jiami
listen 886 ssl; 支持ipv4访问https

listen [::]:886 ssl; 支持ipv6访问https
```
listen       80;
		listen       [::]:80;
```
.
.
.
.
.
.
```
server {
        listen       2096 ssl;
		listen       [::]:2096 ssl;
        server_name  tv.88ija.com;

        ssl_certificate      Q:/nginx-1.21.6/tv.88ija.com.cer;
        ssl_certificate_key  Q:/nginx-1.21.6/tv.88ija.com.key;

        ssl_session_cache    shared:SSL:1m;
        ssl_session_timeout  5m;

        ssl_ciphers  HIGH:!aNULL:!MD5;
        ssl_prefer_server_ciphers  on;

        location / {
            root   html;
            index  index.html index.htm;
        }
    }
```
