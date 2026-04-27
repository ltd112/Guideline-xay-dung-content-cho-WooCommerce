# Hướng dẫn Sử dụng Theme Woodmart

## 1. Cấu hình Hệ thống (Theme Settings)
Quản lý cấu hình tập trung thông qua bảng điều khiển Woodmart.

- **Truy cập**: Dashboard -> **Woodmart** -> **Theme Settings**.
- **Colors (Styles and Colors)**:
    - **Primary color**: Thiết lập mã màu chủ đạo của website.
- **Typography**:
    - Thiết lập Font Family chi tiết cho từng thành phần (Text, Headlines, Navigation).
    - Hỗ trợ tích hợp trực tiếp Google Fonts.
    - **Yêu cầu kỹ thuật**: Đảm bảo độ tương phản (Contrast) đạt tiêu chuẩn **WCAG AA** (tối thiểu 4.5:1) giữa màu chữ và nền để đảm bảo khả năng đọc.

---

## 2. Xây dựng Layout (Elementor & Woodmart Builder)
Sử dụng Elementor phối hợp với các Widget đặc thù của Woodmart.

- **Kiến trúc Container**:
    - **Yêu cầu kỹ thuật**: Mọi khối nội dung phải bắt đầu bằng một **Container**.
    - **Min Height**: Bắt buộc thiết lập chiều cao tối thiểu cho Container trên cả Desktop và Mobile để tối ưu chỉ số LCP.
- **Widget tiêu chuẩn**:
    - **Banner**: Sử dụng widget **Image** hoặc **Image or SVG** đặt trong Container.
    - **Products**: Sử dụng widget **Product (grid/carousel)** để nhúng sản phẩm từ các Collection.
- **Hệ thống Layouts**:
    - Sử dụng **Woodmart -> Layouts** để xây dựng các Template động cho Single Product, Shop, Cart, Checkout.

---

## 3. Quản lý Header (Header Builder)
- **Truy cập**: Dashboard -> **Woodmart** -> **Header Builder**.
- **Tính năng**: 
    - Hỗ trợ kéo thả Element (Logo, Search, Account, Cart).
    - Khả năng tạo nhiều Header và gán theo điều kiện cho từng trang.

---

## 4. Cấu hình Plugin Bổ trợ (WC Enhancement Kit)
Các thiết lập tối ưu riêng cho theme Woodmart:

- **Theme Config**: Bật tùy chọn `Woodmart config` trong dashboard của plugin.
- **Module Optimization**: Khuyên dùng trạng thái Tắt (Disable) cho module Single Product và Pagination của plugin để tránh xung đột với tính năng gốc của Woodmart.

### Variation Display (Hiển thị Biến thể)
- **Enable URL Rewrite**: Tạo Permalinks riêng cho từng biến thể sản phẩm.
- **Force Form Data Loading**: Kích hoạt cơ chế tải trước dữ liệu form thuộc tính.
- **Smart Default Variant**: Tự động kích hoạt biến thể đầu tiên khi tải trang.
- **Swatch Styling**: Cấu hình CSS (Background/Text Color) cho trạng thái Selected tại phần Swatch Settings.

---

## 5. Tài liệu tham khảo
- [Woodmart Documentation](https://xtemos.com/documentation/woodmart/)
