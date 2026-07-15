# Hướng dẫn Sử dụng Plugin EC Product Advanced Fields

> [!NOTE]
> **EC Product Advanced Fields** cung cấp tính năng bổ sung và quản lý các Custom Fields) cho sản phẩm (Ví dụ:  Custom name, Custom number cho các sản phẩm cá nhân hóa).

---

## 1. Truy cập & Quản lý Danh sách Nhóm trường

Để bắt đầu quản lý các nhóm trường nâng cao cho sản phẩm:

- Truy cập vào menu quản trị: **Products ->  EC Advanced Fields**.
- Trang quản lý chính sẽ hiển thị toàn bộ các nhóm trường đã tạo, cho phép bạn xem nhanh tiêu đề, thứ tự ưu tiên (Priority), trạng thái hoạt động (Status) và cung cấp các tùy chọn chỉnh sửa/xóa nhanh.

<div align="center">
    <img src="images/plugin/ec-product-advanced-fields/plugin_product_advanced_field_list.png" alt="Danh sách Product Advanced Fields" />
</div>

---

## 2. Cấu hình Chi tiết Nhóm trường (Advanced Field Settings)

Khi thực hiện tạo mới (**Add New**) hoặc chỉnh sửa một nhóm trường, giao diện cấu hình sẽ được chia thành **3 Tab chính** chuyên nghiệp:

### 2.1. Tab 1: Cấu hình Nhóm (Group Setting)

Thiết lập các thông số cơ bản cho cả nhóm trường:

- **Group Name**: Tiêu đề đại diện của nhóm trường (Ví dụ: *Thông số kỹ thuật điện thoại*).
- **Priority (Thứ tự ưu tiên)**: Thiết lập độ ưu tiên hiển thị. Số càng nhỏ thì nhóm trường này sẽ hiển thị càng cao trong trang biên tập sản phẩm và ngoài frontend.
- **Status (Trạng thái)**: Bật/tắt trạng thái hoạt động của nhóm trường.

<div align="center">
    <img src="images/plugin/ec-product-advanced-fields/plugin_product_advanced_field_group_setting.png" alt="Cấu hình Group Setting" />
</div>

---

### 2.2. Tab 2: Thiết lập Các Trường Con (Fields)

Cho phép định nghĩa chi tiết từng trường dữ liệu cụ thể nằm bên trong nhóm:

- Nhấn **Add Field** để tạo một trường mới.
- **Field Type (Loại dữ liệu)**: Hiện hỗ trợ 2 loại chính:
  * `Text`: Trường nhập văn bản ngắn.
  * `Number`: Trường chỉ cho phép nhập ký tự số.
- **Label (Tiêu đề trường)**: Nhãn hiển thị hướng dẫn người dùng nhập liệu (Ví dụ: *Dung lượng PIN (mAh)*).
- **Placeholder**: Gợi ý nhập liệu mờ hiển thị bên trong ô trống.
- **Description**: Đoạn mô tả giải thích ngắn gọn về trường dữ liệu này.
- **Required (Bắt buộc)**:
  * Nếu kích hoạt, admin buộc phải điền trường này trong sản phẩm, hoặc khách hàng phải điền dữ liệu (nếu cấu hình trường cho frontend).
  * Hệ thống tự động kích hoạt cơ chế kiểm tra (Validate) nghiêm ngặt ngay khi khách hàng nhấn nút **Add to Cart** hoặc **Buy Now**.
- **Validation**: Đặt giới hạn số lượng ký tự nhập vào tối đa (`Max Length`) để tránh làm vỡ giao diện hiển thị.

<div align="center">
    <img src="images/plugin/ec-product-advanced-fields/plugin_product_advanced_field_fields.png" alt="Cấu hình Fields" />
</div>

---

### 2.3. Tab 3: Quy tắc Hiển thị (Display Rule)

Tính năng thông minh giúp tối ưu trải nghiệm nhập liệu cho admin, chỉ hiển thị nhóm trường này cho các sản phẩm đáp ứng đúng điều kiện thiết lập.

- **Quy tắc bộ lọc (Rules)**: Hỗ trợ tạo các điều kiện hiển thị tự động dựa trên:

  * **Product**: Chỉ áp dụng cho một hoặc một vài sản phẩm được chỉ định trong điều kiện.
  * **Category**: Áp dụng cho toàn bộ các sản phẩm thuộc một danh mục cụ thể.
  * **Attribute**: Áp dụng cho các sản phẩm có chứa thuộc tính cụ thể trong điều kiện.
  * **Title**: Áp dụng cho các sản phẩm có chứa một phần tiêu đề có trong điều kiện.
  * **Collection**: Áp dụng cho các sản phẩm thuộc một Collection cụ thể.

<div align="center">
    <img src="images/plugin/ec-product-advanced-fields/plugin_product_advanced_field_display_rule.png" alt="Cấu hình Display Rule" />
</div>
