# Hướng dẫn Sử dụng Theme Woodmart

## 1. Cấu hình Font chữ & Màu sắc
Woodmart quản lý tất cả cấu hình trong bảng điều khiển riêng.

- **Truy cập**: Dashboard -> **Woodmart** -> **Theme Settings**.
- **Màu sắc (Styles and Colors)**:
    - Vào **Styles and Colors** -> **Primary color**.
    - Thiết lập màu chủ đạo.
- **Font chữ (Typography)**:
    - Vào **Typography**.
    - Tại đây bạn có thể thiết lập font cho từng thành phần (Text, Headlines, Navigation).
    - Hỗ trợ Google Fonts mặc định.

---

## 2. Cách tạo Landing Page với Elementor & Woodmart
Woodmart sử dụng Elementor làm trình dựng trang chính. Để tối ưu hóa hiệu suất và tránh lỗi **LCP (Largest Contentful Paint)**, cần tuân thủ quy tắc xây dựng sau:

- **Xây dựng khối kiến trúc (Container)**:
    - Mọi phần của trang phải bắt đầu bằng một **Container**.
    - **Bắt buộc**: Luôn thiết lập **Min Height (Chiều cao tối thiểu)** cho các Container trên cả Desktop và Mobile.   Việc này giúp giữ chỗ cho nội dung, tránh hiện tượng nhảy khung (Layout Shift) và giúp trình duyệt xác định vùng LCP sớm hơn.
- **Thành phần bên trong Container**:
    - **Banner**: Thêm widget **Image** (hoặc Image or SVG) vào trong Container để làm banner.
    - **Sản phẩm (Collections)**: Thêm widget **Product (grid or carousel)** để hiển thị sản phẩm thuộc các bộ sưu tập (Collection) mong muốn.
- **Tính năng Layouts**:
    - Sử dụng **Woodmart -> Layouts** để tạo các mẫu Template cho Single Product, Shop page, Checkout page... giúp đồng bộ giao diện toàn site.

---

## 3. Cấu hình Header Builder
Woodmart có trình dựng Header riêng biệt rất trực quan.
- Truy cập: **Woodmart** -> **Header Builder**.
- Bạn có thể tạo nhiều Header khác nhau và gán cho từng trang cụ thể.
- Hỗ trợ kéo thả các element như Logo, Search, Account, Cart.

---

## 4. Cấu hình Plugin Bổ trợ (WC Enhancement Kit)
Đối với theme Woodmart, cần lưu ý các cấu hình sau trong plugin:

- **Bật Theme Config**: Dashboard -> WC Enhancement Kit -> Dashboard -> Bật Woodmart config.
- **Tắt các module dư thừa**: Tắt Single Product, Pagination và  vì Woodmart đã hỗ trợ rất tốt các phần này.

### Hiển thị Biến thể (Variation Display)
Cấu hình để trang sản phẩm chuyên nghiệp hơn:
1. **Enable URL Rewrite**: Tạo link riêng cho từng biến thể.
2. **Force Form Data Loading**: Tránh lỗi load chậm khi chọn thuộc tính.
3. **Smart Default Variant**: Tự động chọn biến thể đầu tiên.
4. **Style Swatches**: 
   - Tùy chỉnh màu sắc khi option được chọn tại: **Selected Swatch Background** & **Selected Swatch Text Color**.

---

## 5. Tài liệu tham khảo
- Trang chủ tài liệu: [xtemos.com/documentation/woodmart/](https://xtemos.com/documentation/woodmart/)
