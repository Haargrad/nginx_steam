# nginx_steam

put in /etc/nginx/*.conf

```bash
stream {
    upstream hello_rancher_http
    {
        least_conn;
        server 10.0.0.147:30000 max_fails=3 fail_timeout=5s;
        server 10.0.0.148:30000 max_fails=3 fail_timeout=5s;
        server 10.0.0.149:30000 max_fails=3 fail_timeout=5s;
    }
    server
    {
        listen     30000;
        proxy_pass hello_rancher_http;
    }
```
