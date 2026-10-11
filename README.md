# 1. Khởi chạy container
```bash
docker run -d -p 8080:80 --name my-web nginx:alpine
docker ps --filter name=my-web
```
Kết quả:

```text
CONTAINER ID   IMAGE          STATUS                 PORTS                                    NAMES
b6769c5f8245   nginx:alpine   Up Less than a second   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   my-web
```
# 2. Kiểm tra website

```bash
curl -i http://localhost:8080
```

Kết quả:

```text
HTTP/1.1 200 OK
Server: nginx/1.31.6
Content-Type: text/html
```

HTML trả về chứa:

```html
<h1>Welcome to nginx!</h1>
```

Kết quả xác nhận Nginx đã phục vụ website qua cổng 8080 thành công.

## 3. Dừng và xóa container

```bash
docker stop my-web
docker rm my-web
docker ps -a --filter name=my-web
```

Kết quả:

```text
my-web
my-web
CONTAINER ID   IMAGE   COMMAND   CREATED   STATUS   PORTS   NAMES
```

Container my-web đã được dừng và xóa thành công.
