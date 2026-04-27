# Hướng dẫn Sử dụng Theme Flatsome

## 1. Cấu hình Font chữ & Màu sắc
Tất cả các thay đổi về giao diện được thực hiện trong **Customizer**.

- **Truy cập**: Dashboard -> **Appearance** -> **Customize**.
- **Màu sắc (Colors)**:
    - Vào **Style** -> **Colors**.
    - Thiết lập **Primary Color**: Màu chủ đạo.
    - Thiết lập **Secondary Color**: Màu nhấn (thường dùng cho nút, icon).
- **Font chữ (Typography)**:
    - Vào **Style** -> **Typography**.
    - Chọn font cho **Headlines** (Tiêu đề) và **Base** (Nội dung văn bản).
    - Khuyên dùng: *Inter*, *Roboto* hoặc *Montserrat*.

---

## 2. Cách tạo Landing Page với UX Builder
UX Builder cho phép kéo thả các element để tạo trang đẹp mắt.

- **Bước 1**: Tạo trang mới (Pages -> Add New) hoặc Edit trang hiện có.
- **Bước 2**: Nhấn vào nút **Edit with UX Builder**.
- **Các Element quan trọng**:
    - **Section**: Container chính, dùng để chia các khối nội dung lớn. **Lưu ý**: Luôn thiết lập **Min Height** cho Section để tránh lỗi LCP (Largest Contentful Paint).
    - **Row/Column**: Chia cột cho nội dung (vô cùng quan trọng để responsive).
    - **Slider / Banner**: Tạo các khối banner chuyển động hoặc tĩnh.
    - **Text / Headline**: Chèn nội dung văn bản.
    - **Button**: Tạo nút CTA.
- **Lưu ý Responsive**:
    - Nhấp vào biểu tượng Mobile/Tablet ở góc trên UX Builder để kiểm tra hiển thị.
    - Có thể ẩn/hiện các element riêng biệt cho từng thiết bị trong phần **Options -> Visibility**.

---

## 3. Cấu hình Header & Footer
- **Header**: Dashboard -> **Flatsome** -> **Theme Options** -> **Header**. Kéo thả logo, menu, giỏ hàng vào vị trí mong muốn.
- **Footer**: Dashboard -> **Flatsome** -> **Theme Options** -> **Footer**.

---

## 4. Hướng dẫn sử dụng Block
Sử dụng **UX Blocks** để tạo các thành phần nội dung có thể tái sử dụng nhiều nơi (ví dụ: chân trang, thông báo khuyến mãi).
- Truy cập: **UX Blocks** -> Add New.
- Thiết kế bằng UX Builder và lấy Shortcode dán vào vị trí cần hiển thị.
