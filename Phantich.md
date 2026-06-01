## Phần 1 – Phân tích logic

Hiện tại `/products` truy cập được vì:

* Project chưa có dependency:

```gradle
implementation 'org.springframework.boot:spring-boot-starter-security'
```

=> Spring Boot chưa kích hoạt Security Filter.

Do đó:

* mọi request đi thẳng vào Controller
* không có bước xác thực.

---

