  # 📌 Microservices System – User & Content Platform

  Hệ thống gồm nhiều microservice được xây dựng bằng **Java Spring Boot**, sử dụng **Eureka Service Discovery**, **API Gateway**, và **Docker Compose** để chạy toàn bộ hệ thống.

  ---

  ## 📁 Cấu trúc dự án

root/
│── api-gateway/ # API Gateway (Spring Cloud Gateway)
│── content-service/ # Service quản lý nội dung
│── eureka/ # Eureka Service Discovery Server
│── user-service/ # Service quản lý người dùng
│
│── docker-compose.yml # Chạy toàn bộ hệ thống bằng Docker
│── pom.xml # Maven parent pom
│── README.md # File mô tả dự án

yaml
Copy code
---

## 🚀 Sau khi chạy

| Service            | URL / Trạng thái                |
|--------------------|----------------------------------|
| **Eureka Dashboard** | http://localhost:8761           |
| **API Gateway**      | http://localhost:8080           |
| **User Service**     | Đăng ký vào Eureka              |
| **Content Service**  | Đăng ký vào Eureka              |

---

## 🧩 5. Các service

### 🔸 **Eureka Server**
- Cho phép các service đăng ký và tự khám phá (Service Discovery)
- Theo dõi trạng thái của từng service
- Chạy tại cổng **8761**

---

### 🔸 **API Gateway**

**Vai trò:**
- Định tuyến request đến microservice tương ứng
- Hỗ trợ mở rộng: authentication, rate limit, logging,…

**URL truy cập:**
http://localhost:8080

markdown
Copy code

**Routes ví dụ:**
/api/user/** → USER-SERVICE
/api/content/** → CONTENT-SERVICE

yaml
Copy code

---

### 🔸 **User Service**

**Chức năng:**
- Đăng ký  
- Đăng nhập  
- Quản lý người dùng  

**Tên đăng ký lên Eureka:**
USER-SERVICE

yaml
Copy code

---

### 🔸 **Content Service**

**Chức năng:**
- Quản lý bài viết  
- Quản lý nội dung người dùng tạo  

**Tên đăng ký lên Eureka:**
CONTENT-SERVICE

yaml
Copy code

---

## 🧪 6. Chạy thủ công từng service (không Docker)

**Build project:**
```bash
mvn clean install
Chạy từng service:

bash
Copy code
cd eureka
mvn spring-boot:run
bash
Copy code
cd api-gateway
mvn spring-boot:run
bash
Copy code
cd user-service
mvn spring-boot:run
bash
Copy code
cd content-service
mvn spring-boot:run
```

## 📘 7. Mở rộng trong tương lai
- Thêm Authentication Service (JWT/OAuth2)

- Tách Database riêng cho từng service

- Monitoring: Zipkin, Prometheus, Grafana

- Triển khai Kubernetes

- Thêm API Gateway nâng cao như: Kong, Tyk, Traefik

## 👨‍💻 8. Tác giả

Developer: Nguyễn Trọng Kha

Hệ thống mẫu phục vụ học tập và phát triển mô hình microservice của môn kiến trúc phần mềm.
