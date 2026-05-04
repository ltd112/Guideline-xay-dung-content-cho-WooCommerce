# Hướng dẫn Kỹ thuật Theme Flatsome

## 1. Cấu hình Hệ thống (Customizer)
Quản lý giao diện tập trung thông qua WordPress Customizer.

- **Truy cập**: Dashboard -> **Appearance** -> **Customize** -> **Style**.
    <div align="center">
        <img src="images/flatsome/flatsome_appearance_customize.png" alt="Giao diện Customizer Style" />
    </div>

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
    - **Section**: Container bao bọc ngoài cùng của một khối nội dung. **Bắt buộc**: Luôn thiết lập **Min Height** (chiều cao tối thiểu) để ngăn chặn hiện tượng nhảy khung (Layout Shift), đảm bảo ổn định chỉ số LCP.
    - **Row/Column**: Hệ thống lưới (Grid) giúp phân chia tỉ lệ và bố cục nội dung linh hoạt.
    - **Slider/Banner**: Module hiển thị hình ảnh động/tĩnh, cần tối ưu kích thước ảnh phù hợp với khung hình.
    - **Text/Headline**: Các thành phần văn bản, cần tuân thủ hệ thống Typography và đảm bảo độ tương phản màu sắc.
    - **Button**: Các điểm tương tác kêu gọi hành động (CTA).

- **Mô hình cấu trúc Layout mẫu**:
    Một Layout chuẩn trong UX Builder cần tuân thủ tính phân cấp và các yêu cầu kỹ thuật sau:
    - **Cấu trúc phân cấp (Hierarchy)**:
        <div align="center">
            <img src="images/flatsome/flatsome_section.png" alt="Cấu trúc phân cấp UX Builder" />
        </div>
    - **Thiết lập Min Height**: Luôn thiết lập chiều cao tối thiểu cho Section để đảm bảo chỉ số LCP ổn định.
        <div align="center">
            <img src="images/flatsome/flatsome_section_min_height.png" alt="Thiết lập Min Height cho Section" />
        </div>

- **Tối ưu Responsive**:
    - **Viewport Switcher**: Sử dụng trình xem trước (Mobile/Tablet viewport) để kiểm tra bố cục trên đa thiết bị.
    - **Visibility**: Điều chỉnh trạng thái hiển thị (Show/Hide) của từng Element để tối ưu nội dung trên từng loại màn hình.

---

## 3. Quản lý Header & Footer
- **Header Builder**: Dashboard -> **Flatsome** -> **Theme Options** -> **Header**. 
    - **Tính năng**: Cung cấp giao diện kéo thả trực quan để sắp xếp các thành phần như Logo, Menu, Cart, Search vào các vị trí mong muốn trên Header.
    <div align="center">
        <img src="images/flatsome/flatsome_header.png" alt="Giao diện Flatsome Header Builder" />
    </div>

- **Footer Config**: Dashboard -> **Flatsome** -> **Theme Options** -> **Footer**.
    - **Lưu ý tối ưu trải nghiệm người dùng (UX)**: Màu sắc hiển thị trong quá trình tải trang (Initial Load) bị chi phối bởi màu nền của **Absolute Footer**.

---

## 4. Quản lý Khối nội dung (UX Blocks)
Công cụ tạo các thành phần nội dung có khả năng tái sử dụng (Global components).
- **Truy cập**: Dashboard -> **UX Blocks**.
- **Cơ chế**: Thiết kế bằng UX Builder và nhúng vào vị trí bất kỳ qua Shortcode.

## 5. Tài liệu tham khảo
- [Flatsome Documentation](https://docs.uxthemes.com/)
