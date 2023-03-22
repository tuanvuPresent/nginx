# nginx

## Usage

- B1: Tạo file .conf trong folder conf.d theo mẫu sau
    + Sửa lại server_name và IP
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
- B2: Run
```
docker-compose up -d
```


## Http --> https
- Truy cập vào docker container và run
```
apt-get update
```
```
sudo apt-get install certbot
```
```
apt-get install python-certbot-nginx
```

```
certbot --nginx
```

## DNS configuration

![Screenshot](https://user-images.githubusercontent.com/55792941/207835275-9186d71b-650c-403e-b60f-74a1b2d35f8b.png)
