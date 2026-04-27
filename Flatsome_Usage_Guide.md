# Hướng dẫn Kỹ thuật Theme Flatsome

## 1. Cấu hình Hệ thống (Customizer)
Quản lý giao diện tập trung thông qua WordPress Customizer.

- **Truy cập**: Dashboard -> **Appearance** -> **Customize**.
- **Colors (Màu sắc)**:
    - **Primary Color**: Thiết lập mã màu chủ đạo cho toàn bộ website.
    - **Secondary Color**: Thiết lập mã màu bổ trợ cho các thành phần tương tác (Button, Icon).
- **Typography (Font chữ)**:
    - **Headlines**: Cấu hình Font Family cho các thẻ tiêu đề (H1-H6).
    - **Base**: Cấu hình Font Family cho nội dung văn bản mặc định.
    - **Yêu cầu kỹ thuật**: Đảm bảo độ tương phản (Contrast) đạt tiêu chuẩn **WCAG AA** (tối thiểu 4.5:1) giữa màu chữ và nền để đảm bảo khả năng đọc.

---

## 2. Xây dựng Layout (UX Builder)
Công cụ thiết kế kéo thả tích hợp sẵn trong Flatsome.

- **Thành phần cốt lõi (Core Elements)**:
    - **Section**: Container cấp cao nhất. **Yêu cầu kỹ thuật**: Thiết lập **Min Height** để đảm bảo ổn định chỉ số LCP.
    - **Row/Column**: Hệ thống Grid phân chia bố cục nội dung.
    - **Slider/Banner**: Module hiển thị hình ảnh động hoặc tĩnh.
    - **Text/Headline**: Module nhập liệu văn bản.
    - **Button**: Module tạo điểm tương tác CTA.
- **Tối ưu Responsive**:
    - Sử dụng trình xem trước (Mobile/Tablet viewport) để kiểm tra layout.
    - **Visibility**: Điều chỉnh trạng thái hiển thị (Show/Hide) của element trên từng loại thiết bị.

---

## 3. Quản lý Header & Footer
- **Header Builder**: Dashboard -> **Flatsome** -> **Theme Options** -> **Header**. Hỗ trợ kéo thả các element Logo, Menu, Cart.
- **Footer Config**: Dashboard -> **Flatsome** -> **Theme Options** -> **Footer**.

---

## 4. Quản lý Khối nội dung (UX Blocks)
Công cụ tạo các thành phần nội dung có khả năng tái sử dụng (Global components).
- **Truy cập**: Dashboard -> **UX Blocks**.
- **Cơ chế**: Thiết kế bằng UX Builder và nhúng vào vị trí bất kỳ qua Shortcode.
