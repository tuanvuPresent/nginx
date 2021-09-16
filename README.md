# nginx

## Tạo file .conf trong folder conf.d theo mẫu sau

```
server {
    server_name api-example.me;

    location / {
        proxy_pass http://168.62.180.104:8010;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}

```
