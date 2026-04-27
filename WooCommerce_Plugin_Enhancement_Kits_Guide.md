# Hướng dẫn Sử dụng Plugin WC Enhancement Kit

## ⚡ Quick Start

1.  **Product Tabs**: Thêm các tab như "Chính sách đổi trả", "Hướng dẫn sử dụng" cho sản phẩm.
2.  **Variation Display**: Tối ưu cách khách hàng chọn size/màu sắc.
3.  **Collection**: Tạo các bộ sưu tập sản phẩm
4.  **Product Advanced Fields**: Thêm các trường nhập liệu cho khách hàng
5.  **WebP Conversion**: Tự động tối ưu và chuyển đổi ảnh sang WebP khi upload.

---

## 1. Cấu hình Chung & Cài đặt
- **Truy cập**: Dashboard -> **WC Enhancement Kit**.
- **Chọn Template**: Đảm bảo chọn đúng giao diện mẫu tương ứng với theme đang dùng (**Flatsome** hoặc **WoodMart**).

---

## 2. Giao diện Trang Sản phẩm (Single Product UI)
Chỉ áp dụng mạnh mẽ cho theme **Flatsome**. Woodmart nên tắt module này.

- **Nút Buy Now (Mua ngay)**:
    - Cho phép khách hàng đi thẳng đến trang Checkout/Cart.
    - **Position**: Có thể đặt trước hoặc sau nút Add to Cart.
    - **Animation**: Khuyên dùng `Scale` với giá trị `1.05` để tạo hiệu ứng thu hút.
- **Giá sản phẩm (Product Price)**:
    - Ẩn khoảng giá (Price Range) và chỉ hiển thị giá của biến thể đã chọn.
- **Nội dung bổ sung (Extra Content)**:
    - Chèn thêm text hoặc ảnh vào bất kỳ vị trí nào trên trang sản phẩm thông qua các Hook.

---

## 3. Hiển thị Biến thể (Variation Display)
Giúp khách hàng chọn thuộc tính sản phẩm dễ dàng hơn.

- **Smart Default Variant**: Tự động chọn biến thể đầu tiên khi khách vào trang.
- **Force Form Data Loading**: Khuyên dùng để tăng tốc độ phản hồi khi khách click chọn size/màu.
- **Hide Reset Link**: Ẩn chữ "Clear" dư thừa để giao diện sạch sẽ hơn.
- **Selected Swatch Style**: Chỉnh màu nền và màu chữ cho option đang được chọn để làm nổi bật.

---

## 4. Tối ưu ảnh (WebP Conversion)
Module này giúp website tải nhanh hơn bằng cách giảm dung lượng ảnh mà không làm giảm chất lượng.

- **Tự động hóa**: Hệ thống tự động convert mọi ảnh tải lên sang định dạng `.webp`.
- **Bulk Migration (Chuyển đổi hàng loạt)**:
    - Sử dụng khi site có nhiều ảnh cũ chưa được tối ưu.
    - Truy cập card **WebP Conversion** -> Nhấn **Start bulk migration**.
    - Hệ thống sẽ chạy ngầm để xử lý toàn bộ thư viện Media.

---

## 5. Tab Sản phẩm (Product Tabs)

- **Công dụng**: Thêm các thông tin bổ sung mà mặc định WooCommerce không có.
- **Cấu hình**:
    - **Apply for**: Có thể chọn áp dụng cho toàn bộ site, hoặc chỉ một Category/Brand/Sản phẩm nhất định.
    - **Type**: Chọn `Custom` để tự viết nội dung hoặc chọn các tab mặc định.

---

## 6. Bộ sưu tập (Collection)
Tính năng tạo trang danh mục sản phẩm nâng cao, tự động lọc theo điều kiện.

- **Slug**: Mặc định là `/collections/`.
- **Tạo Collection**:
    - **Thumbnail**: Ảnh đại diện trong danh sách.
    - **Banner**: Ảnh hiển thị phía trên trang collection.
    - **Bộ lọc (Filter)**: Lọc sản phẩm theo tiêu đề, giá, ngày đăng hoặc thuộc tính.
- **Sắp xếp (Manual Sort)**: Bạn có thể kéo thả để sắp xếp thứ tự sản phẩm thủ công.

---

## 7. Công cụ Admin & Bảo mật
- **Admin Tool**:
    - Thêm bộ lọc Tag trong trang danh sách sản phẩm.
    - **SEO Quick View**: Xem nhanh thông tin SEO.
- **Product Importer**:
    - Hỗ trợ nhập sản phẩm từ Shopbase hoặc file CSV của WooCommerce.
    - Có cơ chế **Auto-recovery** nếu quá trình nhập bị gián đoạn.

---

## 8. Theo dõi Chuyển đổi (Ads Pixel Manager)
Quản lý các mã tracking cho quảng cáo tại một nơi duy nhất.
- Hỗ trợ: **Google Ads**, **Facebook Pixel (CAPI)**, **Bing Ads**.
- **Lưu ý**: Sau khi thay đổi cấu hình, **BẮT BUỘC** phải xóa cache (WP Rocket) để mã mới có hiệu lực.
