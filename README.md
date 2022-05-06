# nginx-ipv6-jiami
listen 886 ssl; 支持ipv4访问https

listen [::]:886 ssl; 支持ipv6访问https

start nginx 开启nginx服务

（2）nginx.exe -s stop 关闭nginx服务，快速停止nginx，可能并不保存相关信息

（3）nginx.exe -s quit 关闭nginx服务，完整有序的停止nginx，并保存相关信息

(4) nginx.exe -s reload 重载nginx服务，当你改变了nginx配置信息并需要重新载入这些配置时可以使用此命令重载nginx

(5) 使用 taskkill /F /IM nginx.exe > nul命令强关nginx服务器
重新加载配置文件

```
nginx -s reload
```
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
