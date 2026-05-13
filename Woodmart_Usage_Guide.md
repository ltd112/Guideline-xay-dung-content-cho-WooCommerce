# Hướng dẫn Sử dụng Theme Woodmart

## 1. Cấu hình Hệ thống (Theme Settings)
Quản lý cấu hình tập trung thông qua bảng điều khiển Woodmart.

- **Truy cập**: Dashboard -> **Woodmart** -> **Theme Settings**.
- **Colors (Styles and Colors)**:
    - **Primary color**: Thiết lập mã màu chủ đạo của website.
- **Typography**:
    - Thiết lập Font Family chi tiết cho từng thành phần (Text, Headlines, Navigation).
    - Hỗ trợ tích hợp trực tiếp Google Fonts.
    - **Yêu cầu kỹ thuật**: Đảm bảo độ tương phản (Contrast) đạt tiêu chuẩn **WCAG AA** (tối thiểu 4.5:1) giữa màu chữ và nền để đảm bảo điểm số **Accessibility**.

---

## 2. Xây dựng Layout (Elementor & Woodmart Builder)
Sử dụng Elementor phối hợp với các Widget đặc thù của Woodmart để tối ưu hiệu suất và giao diện.

- **Kiến trúc Container**:
    - **Yêu cầu kỹ thuật**: Mọi khối nội dung phải được bao bọc trong một **Container**. Đây là quy tắc bắt buộc để đảm bảo tính đồng nhất và kiểm soát **Min Height**. 
    <div align="center" >
        <img src="images/woodmart/woodmart_container.png" alt="Kiến trúc Container Woodmart"></img> 
    </div>

    - **Min Height**: Bắt buộc thiết lập chiều cao tối thiểu cho Container trên cả Desktop và Mobile. Điều này giúp trình duyệt xác định trước không gian hiển thị, ngăn chặn hiện tượng nhảy khung hình và tối ưu chỉ số LCP.
    <div align="center" >
        <img src="images/woodmart/woodmart_container_min_height.png" alt="Thiết lập Min Height cho Container" ></img>
    </div>

- **Widget tiêu chuẩn**:
    - **Banner**: Sử dụng widget **Image** hoặc **Image or SVG** đặt trong Container để kiểm soát tỉ lệ hiển thị.
    - **Products**: Sử dụng widget **Product (grid/carousel)** để nhúng sản phẩm từ các Collection linh hoạt. 
    <div align="center" >
        <img src="images/woodmart/woodmart_element_collection_product.png" alt="Widget Collection Product Woodmart" ></img>
    </div>
    
- **Hệ thống Layouts**:
    - Truy cập **Woodmart -> Layouts** để xây dựng các Template động cho Single Product, Shop, Cart, Checkout, giúp quản lý giao diện tập trung.

---

## 3. Quản lý Header (Header Builder)
Woodmart cung cấp trình xây dựng Header mạnh mẽ với cơ chế kéo thả trực quan.

- **Truy cập**: Dashboard -> **Woodmart** -> **Header Builder**.
- **Tính năng chủ chốt**: 
    - **Cơ chế kéo thả**: Dễ dàng sắp xếp các Element như Logo, Search, Account, Cart vào các hàng (Rows) khác nhau.
    <div align="center" >
        <img src="images/woodmart/woodmart_header.png" alt="Giao diện Woodmart Header Builder" ></img>
    </div>
    
    - **Header linh hoạt**: Khả năng tạo nhiều Header khác nhau và gán theo điều kiện (Condition) cho từng trang (ví dụ: Header riêng cho trang chủ và trang cửa hàng).

---

## 4. Cấu hình Plugin Bổ trợ (WC Enhancement Kit)
Truy cập plugin thông qua **Settings -> WC Enhancement Kit**.

### 4.1. Tối ưu hóa Module (Module Optimization)
- **Theme Config**: Bật tùy chọn **Woodmart config** trong dashboard của plugin.
- **Module Optimization**: Khuyên dùng trạng thái **Disable** cho các module **Single Product** và **Pagination** và các module **Legacy** của plugin để tránh xung đột với tính năng gốc của Woodmart.

### 4.2. Hiển thị Biến thể (Variation Display)
- **Enable URL Rewrite**: Tạo **Permalinks riêng** cho từng biến thể sản phẩm.
- **Force Form Data Loading**: Kích hoạt cơ chế **tải trước dữ liệu form thuộc tính**.
- **Smart Default Variant**: Tự động **kích hoạt biến thể đầu tiên** khi tải trang.
- **Swatch Styling**: Cấu hình **CSS** (Background/Text Color) cho trạng thái **Selected** tại phần Swatch Settings.
    <div align="center" >
        <img src="images/plugin/wc-enhancement-kit/plugin_variant_display.png" alt="Cấu hình hiển thị biến thể trong Woodmart" ></img>
    </div>
    
---

## 5. Cấu hình Swatches cho Thuộc tính (Attributes - Gốc của Woodmart)
Để thay thế danh sách thả xuống mặc định ngoài frontend bằng các ô chọn màu sắc hoặc kiểu dáng (Swatches) trực quan bằng tính năng gốc cực kỳ mạnh mẽ của Woodmart, hãy thực hiện theo quy trình sau:

### 5.1. Cấu hình cấp Thuộc tính (Global Settings)
- **Truy cập**: Dashboard -> **Products** -> **Attributes**.
- **Thao tác**: Chọn thuộc tính cần cấu hình (ví dụ: **Size**) và nhấn **Edit**.
    <div align="center" >
        <img src="images/woodmart/attribute-step-1.png" alt="Cấu hình Attribute Swatch trong Woodmart" ></img>
    </div>
- **Các thông số quan trọng**:
    - **Swatch style**: Thiết lập kiểu hiển thị khi chọn biến thể.
    - **Disabled swatch style**: Trạng thái hiển thị khi biến thể hết hàng.
    - **Swatch shape**: Hình dạng của ô chọn (Rounded hoặc Square).
    - **Swatch size**: Kích thước hiển thị (XS, S, M, L, XL).
    <div align="center" >
        <img src="images/woodmart/woodmart_attribute_swatch.png" alt="Cấu hình Attribute Swatch trong Woodmart" ></img>
    </div>
- **Lưu cấu hình**: Sau khi thiết lập xong các thông số trên, cuộn xuống dưới cùng và nhấn nút **Update** để lưu lại cấu hình cấp thuộc tính.
    
### 5.2. Cấu hình giá trị hiển thị (Configure Terms)
- **Quay lại danh sách thuộc tính**: Sau khi nhấn *Update* ở bước 5.1, click vào liên kết **Attributes** ở menu bên trái (trong mục **Products -> Attributes**) để quay lại bảng danh sách thuộc tính tổng quát.
- **Thao tác**: Tìm thuộc tính **Size** trong bảng danh sách, di chuột đến cột ngoài cùng bên phải và click vào liên kết **Configure terms** của dòng Size đó.
    <div align="center" >
        <img src="images/woodmart/attribute-step-2.png" alt="Cấu hình giá trị Swatch chi tiết" ></img>
    </div>
- **Kích hoạt giá trị cụ thể**: 
  - Tại bảng danh sách các giá trị thuộc tính Size hiện ra (ví dụ: *S, M, L, XL*), click nút **Edit** bên dưới giá trị muốn chỉnh sửa (ví dụ: **L**).
  
  - Tùy chỉnh bật tùy chọn **Enable text swatch** hoặc thiết lập mã màu/ảnh minh họa cụ thể cho giá trị này.
    <div align="center" >
        <img src="images/woodmart/woodmart_attribute_value_swatch.png" alt="Cấu hình giá trị Swatch chi tiết" ></img>
    </div>
- **Lưu cấu hình**: Sau khi cập nhật giá trị màu sắc, chữ hoặc hình ảnh minh họa cho term, cuộn xuống dưới cùng và nhấn nút **Update** (hoặc **Save Changes**) để áp dụng các thay đổi hiển thị ra ngoài frontend.

---

## 6. Tài liệu tham khảo
- [Woodmart Documentation](https://xtemos.com/documentation/woodmart/)
- [Công cụ kiểm tra độ tương phản](https://webaim.org/resources/contrastchecker/)
