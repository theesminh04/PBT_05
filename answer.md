### PHIẾU BÀI TẬP 05
### CSS RESPONSIVE & SCSS — Responsive Design, Media Queries, Sass
--- 

### PHẦN A — KIỂM TRA ĐỌC HIỂU (20 điểm)
### Câu A1 (5đ) — Viewport & Mobile-First
- Viết chính xác thẻ <meta viewport> chuẩn. Giải thích từng thuộc tính.  
  1. Thẻ < meta viewport > chuẩn  :   
  + < meta name="viewport" content="width=device-width, initial-scale=1.0" >  
  + Trong đó, width=device-width đặt chiều rộng viewport bằng chiều rộng thật của thiết bị, còn initial-scale=1.0 đặt mức zoom ban đầu là 100%.  
  + Thẻ này đặt trong phần <head> của file HTML

- Nếu THIẾU thẻ này, iPhone sẽ hiển thị trang web như thế nào? (Đọc chương 13)  
  + iPhone thường giả lập trang như một trang desktop rộng khoảng 980px và thu phóng sao cho vừa màn hình khiến cho chữ bị nhỏ và phải zoom để nhìn.  
  
- Mobile-First và Desktop-First khác nhau thế nào? Viết ví dụ CSS cho mỗi cách với breakpoint 768px. Tại sao Mobile-First được khuyên dùng?  
  
  + Mobile-First là viết CSS cho mobile trước, sau đó dùng @media (min-width: 768px) để mở rộng cho màn hình lớn.   
  
  + Desktop-First là viết CSS cho desktop trước, sau đó dùng @media (max-width: 767px) để chỉnh lại cho mobile.   
  
  + Mobile-First được khuyên dùng vì phù hợp với thói quen dùng điện thoại hiện nay, giúp giao diện gọn hơn, ưu tiên nội dung quan trọng và thường có hiệu năng tốt hơn trên thiết bị di động.

### Câu A2 (5đ) — Ghi lại breakpoints chuẩn (theo tài liệu hoặc Bootstrap). Cho mỗi breakpoint:

| Breakpoint | Kích thước (Pixel) | Thiết bị đại diện | Ví dụ: Số cột lưới sản phẩm |
| :--- | :---: | :---: | ---: |
| Extra Small (xs) | < 576px | Điện thoại di động (đứng) | 1 cột |
| Small (sm) | ≥ 576px | Điện thoại (nằm ngang), Tablet nhỏ | 2 cột |
| Medium (md) | ≥ 768px | Máy tính bảng (Tablet) | 3 cột |
| Large (lg) | ≥ 992px | Laptop, Máy tính để bàn nhỏ | 4 cột |
| Extra Large (xl) | ≥ 1200px | Màn hình Desktop tiêu chuẩn | 4 hoặc 5 cột |
| Extra Extra Large (xxl) | ≥ 1400px | Màn hình lớn, Độ phân giải cao | 6 cột |

### Câu A3 (5đ) — Media Queries
Đọc CSS sau, cho biết ở mỗi kích thước màn hình, .container có width bao nhiêu? Điền bảng.  

| Chiều rộng màn hình | .container width | 
| :---: | :---: |  
| 375px (iPhone SE) | 	375px |
|600px|	540px|
|800px|	720px|
|1000px|	960px|
|1400px|	1140px|

### Câu A4 (5đ) — SCSS Basics
Đọc chương 16. Giải thích 4 tính năng chính của SCSS và cho ví dụ:

| Tính năng | Giải thích | Ví dụ Code |
| :---: | :---: | :---: |
| Variables (Biến) | 	Cho phép lưu trữ các giá trị (màu sắc, font, kích thước) vào một cái tên bắt đầu bằng dấu $. Khi cần đổi màu cả website, bạn chỉ cần sửa ở 1 nơi. | $primary-color: #ff5733; button { background: $primary-color; } | 
|Nesting (Lồng nhau)|	Viết các selector con bên trong selector cha, giống hệt cấu trúc của HTML. Giúp code gọn gàng, dễ quản lý hơn hẳn.| nav {ul { list-style: none; } li { display: inline-block; } } | 
|Mixins|	Là những "khối code" mẫu có thể tái sử dụng nhiều lần. Nó giống như một hàm, thậm chí có thể truyền tham số vào để tùy biến. | @mixin flex-center {display: flex;align-items: center; } .box { @include flex-center; } |
|@extend / Inheritance | Giúp một selector "kế thừa" toàn bộ thuộc tính của một selector khác. Rất hữu ích để tránh lặp code cho các thành phần tương tự nhau. | .btn { padding: 10px; border: 0; } .btn-save { @extend .btn; background: green;}  



- Tại sao trình duyệt KHÔNG đọc được file .scss? Cần bước gì để chuyển SCSS   → CSS?  
    + Các trình duyệt như google, edge,.... chỉ hiểu được CSS mà file
SCSS không phải là CSS chuẩn mà là những cú pháp đặc biệt gồm
biến, lồng,.... mà cơ chế của trình duyệt không xử lý được.

   + Bước để chuyển SCSS sang CSS là biên dịch với các bước sau 
Viết code trong file .scss -> chạy công cụ biên dịch -> công cụ sẽ 
tạo ra file .css tương ứng từ file scss -> nhúng file .css mới vào
file HTML để sử dụng. 