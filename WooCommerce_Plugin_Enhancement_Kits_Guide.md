# Hướng dẫn Sử dụng Plugin WC Enhancement Kit

> Đây là các điểm cần lưu ý chính khi sử dụng plugin. Tài liệu hướng dẫn sử dụng chi tiết và đầy đủ có tại: [Google Docs - WC Enhancement Kit Guide](https://docs.google.com/document/d/1nW-ad7lRfS3UATdKyQ0E3tejxrnFDEB6zzRJFmpT4Uw/edit?usp=sharing)

## Quick Start

1.  **Product Tabs**: Module quản lý tab thông tin bổ sung.
2.  **Variation Display**: Tối ưu hóa giao diện chọn thuộc tính.
3.  **Collection**: Công cụ tạo danh mục sản phẩm động.
4.  **Product Advanced Fields**: Thêm các trường dữ liệu tùy chỉnh.
5.  **WebP Conversion**: Tự động tối ưu hóa định dạng ảnh.

---

## 1. Cấu hình Chung & Cài đặt
- **Truy cập**: Dashboard -> **WC Enhancement Kit**.
- **Chọn Template**: Đảm bảo chọn đúng giao diện mẫu tương ứng với theme đang dùng (**Flatsome** hoặc **WoodMart**).
---

## 2. Giao diện Trang Sản phẩm (Single Product UI)
Module tối ưu hiển thị, chỉ khả dụng cho theme **Flatsome**.

- **Buy Now Button**:
    - **Position**: Hỗ trợ thay đổi vị trí nút (Trước hoặc Sau nút Add to Cart).
    - **Animation**: Cấu hình loại hiệu ứng (Animation Type) và tỷ lệ thu phóng (Scale).
- **Product Price**:
    - **Price Range**: Chức năng ẩn khoảng giá (Min - Max price) của sản phẩm có biến thể.
    - **Variation Price**: Hiển thị giá cụ thể của biến thể đã chọn.
- **Extra Content**:
    - **Hooks**: Hỗ trợ chèn nội dung (Text, Image, HTML) vào các vị trí Hook trên trang sản phẩm.
---

## 3. Hiển thị Biến thể (Variation Display)
Module quản lý và tối ưu hóa trình chọn thuộc tính sản phẩm.

- **Smart Default Variant**: Tự động chọn biến thể đầu tiên khi tải trang.
- **Force Form Data Loading**: Kích hoạt cơ chế tải trước dữ liệu để tăng tốc độ phản hồi khi khách hàng chọn option.
- **Hide Reset Link**: Ẩn liên kết "Clear/Xóa" mặc định của WooCommerce.
- **Selected Swatch Style**: Tùy chỉnh màu sắc (Color/Background) cho trạng thái đang được chọn (Active state) của Swatch.

---

## 4. Tối ưu ảnh (WebP Conversion)
Module chuyển đổi định dạng ảnh sang WebP để tối ưu tốc độ tải trang.

- **Auto Conversion**: Hệ thống tự động chuyển đổi mọi ảnh upload sang `.webp`.
- **Bulk Migration**:
    - Chức năng quét và xử lý hàng loạt ảnh cũ chưa được tối ưu.
    - Quy trình chạy ngầm (Background processing) thông qua bảng điều khiển WebP Conversion.

---

## 5. Tab Sản phẩm (Product Tabs)
Module mở rộng thông tin sản phẩm thông qua các tab tùy chỉnh.

- **Apply For**: Cấu hình phạm vi hiển thị (Toàn trang, Danh mục, Thương hiệu hoặc Sản phẩm cụ thể).
- **Tab Type**: Hỗ trợ loại `Default` (có sẵn) hoặc `Custom` (tự định nghĩa nội dung).

---

## 6. Bộ sưu tập (Collection)
Tính năng tạo trang danh sách sản phẩm nâng cao với quy tắc lọc động.

- **URL Slug**: Cấu hình đường dẫn tĩnh (mặc định: `/collections/`).
- **Collection Fields**:
    - **Media**: Thiết lập ảnh Thumbnail và Banner cho từng bộ sưu tập.
    - **Filters**: Thiết lập tiêu chí lọc sản phẩm (Price, Date, Attribute, Title).
- **Product Sorting**: Hỗ trợ sắp xếp thủ công (Manual drag-drop) thứ tự sản phẩm.

---

## 7. Công cụ Admin & Nhập liệu
- **Admin Tool**:
    - **Product Tags Filter**: Thêm bộ lọc thẻ (Tags) vào trang danh sách sản phẩm.
    - **SEO Quick View**: Tích hợp xem nhanh dữ liệu SEO.
- **Product Importer**:
    - Hỗ trợ định dạng Shopbase và WooCommerce CSV.
    - **Auto-recovery**: Cơ chế tự động khôi phục quy trình nếu bị gián đoạn.

---

