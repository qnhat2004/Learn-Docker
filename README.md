![](/imgs/docker-img.png)
# Các lệnh cơ bản trong Docker

## Image
- Docker Image là một tập hợp các tệp và các hướng dẫn được sử dụng để tạo ra một Docker container. Nó chứa mọi thứ cần thiết để chạy một ứng dụng, bao gồm mã nguồn, thư viện, phụ thuộc, tệp cấu hình và các công cụ cần thiết. Docker image là bản sao hoàn chỉnh và có thể chạy độc lập của một ứng dụng.

### Liệt kê các images
```bash
docker images
```
### Tìm kiếm các images
```bash
docker search keyword
```

### Tải về image
```bash
docker pull image:tag
```

### Xóa image
```bash
docker image rm <image_name_or_id>
```

## Container
- Container là phiên bản thực thi của images

### run -it: i-interactive: nhận tương tác, t-terminal: chạy trong terminal. Sử dụng khi muốn tương tác trực tiếp với container thông qua 1 terminal, giúp gỡ lỗi và chạy các lệnh bên trong container một cách thủ công.
```bash
docker run -it <image-id-or-name>
```

### run -dp: d-detached mode: chạy ở chế độ nền, cho phép tiếp tục sử dụng terminal cho các công việc khác. p-publish: '-p <host_port>:<container_port> cho phép truy cập dichj vụ chạy bên trong container từ máy chủ.
### Chạy 1 container lần đầu tiên
```bash
docker run -dp <host_port>:<container_port> hub-username/image-name
```

### Khởi chạy 1 container với tên cụ thể và host name cụ thể, tương tác trực tiếp với container thông qua terminal
```bash
docker run -it --name <NAME> -h <HOST> image
```

### Liệt kê các container đang chạy
```bash
docker ps 
```

### Liệt kê tất cả container kể cả đang không chạy
```bash
docker ps -a
```

### Dừng container 
```bash
docker stop <container_id_or_name>
```

### Khởi động lại container đã dừng
```bash
docker start <container-id_or_name>
```

### Truy cập vào container đang chạy
```bash
docker attach <container-id_or_name>
```

### Thoát container nhưng vẫn giữ nó chạy
```
Ctrl P Q
```

### Xóa container đã dừng
```bash
docker rm <container-id_or_name>
```

### Xóa container đang chạy
```bash
docker rm -f <container-id_or_name>
```

### Xóa tất cả container
```bash
docker rm -f $(docker ps -aq)
```
