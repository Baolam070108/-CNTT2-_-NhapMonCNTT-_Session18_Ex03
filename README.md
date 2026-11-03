1. VẤN ĐỀ LÀ GÌ?

- **Giao diện theo dõi lộ trình xe bị lỗi chồng lấn giữa khung "Thông tin tài xế" và "Danh sách trạm", khiến bố cục hiển thị không đúng.**

2. YÊU CẦU LÀ GÌ?

- **Chức năng 1 (Định vị phần tử):** Sử dụng tính năng Inspect Element để định vị chính xác thẻ HTML bị lỗi trong cây DOM Tree.

- **Chức năng 2 (Tối ưu Layout):** Phân tích 4 lớp của CSS Box Model (Content, Padding, Border, Margin) để tách biệt hai khung nội dung.

3. CÁCH LÀM:

- Phần 1. Phân tích:

+ Nhấn F12, chọn Inspect Element và nhấn vào khung bị lỗi trong giao diện.
+ Quan sát thẻ HTML tương ứng trong DOM Tree.
+ Chọn tab Computed để xem 4 lớp Box Model:
  * Content: Nội dung bên trong.
  * Padding: Khoảng cách từ nội dung đến viền.
  * Border: Đường viền phần tử.
  * Margin: Khoảng cách bên ngoài phần tử.
+ Kiểm tra các thông số để xác định nguyên nhân gây chồng lấn.

- Phần 2. Triển khai:

Trong tab Styles, thử điều chỉnh CSS:
  * margin: 10px;
  * padding: 15px;
  * border: 1px solid black;
  * position: static;
  * width: 100%;
Có thể bổ sung box-sizing: border-box để kiểm soát kích thước phần tử tốt hơn.
Các thay đổi được áp dụng trực tiếp trên DevTools, không làm thay đổi file mã nguồn gốc.

- Phần 3. Kiểm thử:

Nếu thay đổi Margin nhưng phần tử vẫn không di chuyển:
+ Kiểm tra thuộc tính position như absolute hoặc fixed.
+ Kiểm tra các thuộc tính top, left, right, bottom.
+ Kiểm tra xem có quy tắc CSS khác đang ghi đè hay không.
+ Kiểm tra thuộc tính !important và các kiểu mặc định từ Browser Engine.
Sau đó điều chỉnh hoặc tắt quy tắc CSS gây xung đột trong tab Styles.
