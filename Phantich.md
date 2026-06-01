Khi truy cập /products, hệ thống trả về danh sách sản phẩm mà không cần đăng nhập vì project chưa tích hợp Spring Security.

Nguyên nhân chính:

Project chưa có dependency spring-boot-starter-security

nên Spring Boot không tạo Security Filter Chain để chặn request.

Luồng hiện tại:

Client gọi /products
↓
Spring Boot chuyển thẳng request vào ProductController
↓
Method getAllProducts() chạy
↓
Trả về danh sách sản phẩm

Controller hiện tại:

@GetMapping("/products")
public List<String> getAllProducts() {
return Arrays.asList("Laptop Thinkpad", "Mouse Logitech", "Keyboard Akko");
}

Vì không có bước xác thực nên bất kỳ ai biết URL /products đều xem được dữ liệu.