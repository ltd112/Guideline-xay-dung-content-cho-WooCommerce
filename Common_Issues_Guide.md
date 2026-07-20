# Hướng Dẫn Khắc Phục Các Lỗi Thường Gặp Trên Flatsome và Woodmart (General Troubleshooting Guide)

Tài liệu này tổng hợp các lỗi kỹ thuật, giao diện và hiệu năng phổ biến nhất mà các website WooCommerce sử dụng theme **Flatsome** và **Woodmart** thường gặp phải trong thực tế, cùng giải pháp khắc phục chi tiết cho từng trường hợp.

---

## 1. Các Lỗi Phổ Biến Trên Theme Flatsome (Flatsome Theme)

### 1.1. Lỗi: Trang chi tiết sản phẩm trên Mobile bị trượt, kéo ngang qua lại và không cố định

* **Triệu chứng**: Khi xem trang chi tiết sản phẩm bằng điện thoại di động (Mobile), giao diện trang có thể bị kéo trượt, xê dịch qua lại theo chiều ngang (bị tràn khung ngang) thay vì hiển thị cố định, vừa vặn khít với màn hình.
* **Nguyên nhân**: Do một số thành phần CSS hoặc phần tử HTML trong trang sản phẩm có kích thước thực tế vượt quá độ rộng màn hình thiết bị di động (100vw).
* **Cách khắc phục**: Thêm đoạn code CSS sửa lỗi vào tệp CSS của Flatsome Child Theme bằng một trong các phương thức truy cập sau:
  * **Đường dẫn tệp tin**`wp-content/themes/flatsome-child/asset/custom.css`
  * **Truy cập từ Dashboard**: **Appearance (Giao diện) -> Customize (Tùy biến) -> Additional CSS (CSS bổ sung)**.
  * **Với các trang sản phẩm sử dụng giao diện / Layout mặc định của Flatsome**:

    ```css
    .product-container {
        max-width: 100vw;
        overflow-x: hidden;
    }
    ```
  * **Với các website thuộc danh sách site Strikerkit** (do tự xây dựng custom lại layout trang sản phẩm riêng biệt):

    ```css
    .custom-product-page {
        max-width: 100vw;
        overflow-x: hidden;
    }
    ```

### 1.2. Lỗi: Menu quá dài đẩy giao diện tạo khoảng trống trắng thừa ở các trang ngắn

* **Triệu chứng**: Khi truy cập vào các trang có nội dung ngắn (như trang liên hệ, giỏ hàng trống), giao diện xuất hiện khoảng trống trắng rất lớn ở chân trang, làm bố cục trang bị kéo giãn mất thẩm mỹ.
* **Nguyên nhân**: Khi danh mục sản phẩm hoặc menu dọc (Vertical Menu) của Flatsome có quá nhiều mục con xếp chồng theo chiều dọc. Nếu chiều cao menu lớn hơn nội dung trang, nó sẽ đẩy footer xuống dưới, tạo ra khoảng trống thừa.
* **Cách khắc phục**: Tách biệt hệ thống menu thành hai phiên bản cho Desktop và Mobile:
  1. **Trên Desktop**: Sử dụng **UX Blocks** kết hợp **UX Builder** để thiết kế **Mega Menu** dàn hàng ngang (Grid columns).
     - Tạo một UX Block mới tại **Dashboard -> UX Blocks -> Add New** và dựng giao diện menu chia cột.
     - Liên kết UX Block này vào menu cha trong **Appearance (Giao diện) -> Menus**.
  2. **Trên Mobile**: Sử dụng menu dạng cây dọc lồng nhau (Accordion) truyền thống để người dùng dễ vuốt cuộn trên điện thoại.
  3. **Kết luận**: Cần thiết lập **2 menu riêng biệt** phục vụ cho Desktop và Mobile trong cấu hình Flatsome Header.

### 1.3. Lỗi nhảy khung hình, giật trang (Chỉ số CLS cao) trên Google PageSpeed Insights

* **Triệu chứng**: Khi tải trang, các khối nội dung, hình ảnh hoặc banner bị dịch chuyển đột ngột gây khó chịu cho người dùng và giảm điểm tối ưu hóa SEO.
* **Nguyên nhân**: Các phần tử như **Section**, **Banner**, hoặc **Slider** trong UX Builder không được chỉ định chiều cao tối thiểu (`Min Height`), khiến trình duyệt phải tính toán lại kích thước sau khi ảnh tải xong.
* **Cách khắc phục**:
  1. Mở trang bằng UX Builder.
  2. Nhấp vào các khối **Section**, **Banner** ở đầu trang và thiết lập thông số **Min Height** cụ thể (Ví dụ: `500px` trên Desktop và `300px` trên Mobile).
  3. Sử dụng định dạng ảnh WebP nhẹ và thiết lập thuộc tính chiều rộng/chiều cao cố định cho ảnh.

### 1.4. Lỗi không dịch được văn bản hiển thị của nút "Add to Cart" (Thêm vào giỏ) và "Buy Now" (Mua ngay)

* **Triệu chứng**: Khi chuyển đổi đa ngôn ngữ cho website, nhãn chữ trên nút "Add to Cart" hoặc "Buy Now" trên trang chi tiết sản phẩm / trang cửa hàng vẫn giữ nguyên tiếng Anh (hoặc ngôn ngữ cũ) mà không dịch theo.
* **Nguyên nhân**: Các nút bấm này do plugin **WC Enhancement Kit (WCEK)** khởi tạo động và nhãn văn bản được lưu tĩnh trực tiếp trong phần cài đặt của plugin thay vì sử dụng cơ chế dịch qua tệp PO/MO mặc định của theme.
* **Cách khắc phục**:
  1. Truy cập **Dashboard -> Enhancement Kit -> Quick Purchase & AJAX Setting**.
  2. Để dịch nút **Buy Now**: Vào tab **Buy Now**, tìm trường **Button Text** và điền văn bản mới tương ứng với ngôn ngữ mong muốn (ví dụ: "Mua Ngay").
  3. Để dịch nút **Add to Cart**: Vào tab **Add to Cart Ajax**, tìm trường **Button Text** và nhập nhãn chữ mong muốn (ví dụ: "Thêm vào giỏ hàng").
  4. Nhấn **Save Settings** để áp dụng.

### 1.5. Lỗi hiển thị sai chữ nút "Add to Cart" tại popup Quick View trên các trang đa ngôn ngữ Flatsome

* **Triệu chứng**: Khi chuyển sang ngôn ngữ khác (ví dụ tiếng Đức), nút thêm vào giỏ hàng tại popup Quick View (Xem nhanh) của Flatsome hiển thị sai nhãn chữ thành "Schnellansicht" (Xem nhanh) thay vì nhãn mong muốn là "In Den Warenkorb" (Thêm vào giỏ).
* **Nguyên nhân**: Bản dịch gettext của WordPress dịch nhầm ngữ cảnh từ khóa hoặc do theme không đồng nhất chuỗi ký tự dịch cho popup Quick View.
* **Cách khắc phục**:
  Chèn thêm đoạn code bộ lọc dịch vào tệp `custom-hook` của Flatsome Child Theme (tệp này đã được dựng cấu trúc sẵn trong mã nguồn):

  ```php
  add_filter( 'gettext', function ( $strings ) {
      $text = array('Schnellansicht' => 'In Den Warenkorb');
      $strings =  str_ireplace(array_keys($text), $text, $strings);
      return $strings;
  }, 20);
  ```

  *(Áp dụng phương pháp này cho mọi website chạy Flatsome gặp lỗi tương tự để thay thế chuỗi ký tự bị dịch sai theo thời gian thực).*

### 1.6. Lỗi không tự động dịch hoặc tùy biến được khối biểu tượng thanh toán (Payment Options) trên trang sản phẩm

* **Triệu chứng**: Khối hiển thị hình ảnh các phương thức thanh toán an toàn (Payment Badges / Trust Badges) trên trang chi tiết sản phẩm hiển thị nhãn chữ bị gán cứng (hardcoded), không thay đổi ngôn ngữ khi dịch web hoặc không thể ẩn bớt các biểu tượng thanh toán không dùng.
* **Nguyên nhân**: Mã HTML của phần này sử dụng chuỗi tĩnh không hỗ trợ dịch động qua tệp PO/MO.
* **Cách khắc phục**:
  - Khi cần thay đổi nội dung văn bản dịch hoặc ẩn/bớt số lượng hình ảnh icon thanh toán, hãy truy cập vào tệp `custom-hook` hoặc `custom-shortcode` của Flatsome Child Theme.
  - Tìm đến hàm (function) `ec_custom_payment_options_html` đã được định nghĩa sẵn và tiến hành chỉnh sửa thủ công chuỗi văn bản HTML, hoặc ẩn bớt các thẻ hình ảnh (img) của phương thức thanh toán tại đây.

### 1.7. Lỗi nút bảng size (Size Guide / Size Charts) hiển thị sai vị trí mong muốn

* **Triệu chứng**: Nút mở bảng size hiển thị ở dưới cùng sau khối chọn biến thể (Variant block) thay vì hiển thị ngay cạnh nhãn chọn Size hoặc vị trí mong muốn.
* **Nguyên nhân**: Chưa chỉ định thuộc tính kích thước trong phần cấu hình thuộc tính kích thước (Size Attributes) của plugin. Khi để trống, plugin mặc định hiển thị ở dưới cùng sau khối chọn biến thể.
* **Cách khắc phục**:
  1. Truy cập **Dashboard -> Enhancement Kit -> Size Charts** -> Chọn nút **Settings** (Cài đặt).
  2. Tại trường cấu hình **Size Attributes**, hãy nhập đúng tên thuộc tính kích thước đang sử dụng trên trang (ví dụ: `Size` hoặc `pa_size`).
  3. Nhấn lưu lại. Nút bảng size sẽ tự động dịch chuyển lên vị trí cạnh thuộc tính kích thước đã cấu hình.

### 1.8. Lỗi hình ảnh trong khối "Related Products" (Sản phẩm liên quan) hiển thị không đồng đều

* **Triệu chứng**: Các hình ảnh sản phẩm trong phần "Related Products" ở chân trang chi tiết sản phẩm hiển thị kích thước cao thấp không đều, làm lệch bố cục hàng sản phẩm.
* **Nguyên nhân**: Do kích thước tải lên của các ảnh gốc không cùng tỷ lệ (ví dụ ảnh dọc, ảnh ngang lộn xộn).
* **Cách khắc phục**:
  Bổ sung đoạn code CSS sau vào tệp tin CSS của Flatsome Child Theme (sử dụng các phương thức truy cập đã nêu ở mục 1.1) để ép ảnh về tỷ lệ vuông 1:1 đồng nhất:
  ```css
  .related-products-wrapper img {
      aspect-ratio: 1 / 1;
      object-fit: cover;
  }
  ```

### 1.9. Lỗi: Tải lại trang (reload) bị đổi màu nền trang theo màu của Bottom Footer

* **Triệu chứng**: Khi người dùng tải lại trang (reload / refresh), màu nền toàn bộ trang web bị chuyển hoặc nhấp nháy sang màu của chân trang dưới cùng (Bottom Footer / Absolute Footer) rồi mới hiển thị bình thường.
* **Nguyên nhân**: Trong mã nguồn của theme Flatsome, tệp CSS động gán chung màu nền `footer_bottom_color` cho cả class `.absolute-footer` và thẻ `html`. Việc áp dụng màu nền footer cho thẻ `html` gây ra hiện tượng nền trang đổi sang màu footer khi trang đang được nạp lại.
* **Cách khắc phục**:
  Chỉnh sửa trực tiếp tệp tin mã nguồn trong theme Flatsome tại đường dẫn `flatsome/inc/functions/function-custom-css.php` (dòng 577 - 579):

  * **Mã gốc bị lỗi**:

    ```php
    <?php if(get_theme_mod('footer_bottom_color')){ ?>
    .absolute-footer, html{background-color: <?php echo get_theme_mod('footer_bottom_color') ;?>}
    <?php } ?>
    ```
  * **Mã sửa lại (Fix)**:

    ```php
    <?php if(get_theme_mod('footer_bottom_color')){ ?>
    .absolute-footer {background-color: <?php echo get_theme_mod('footer_bottom_color') ;?>}
    <?php } ?>
    	html {
    		background-color: #fff !important;
    	}
    ```

  *(Lưu ý: Tách thuộc tính `html` ra khỏi selector `.absolute-footer` để không bị áp dụng màu `footer_bottom_color` cho thẻ `html`, đồng thời quy định màu nền mặc định cho `html` là `#fff !important`).*

---

## 2. Các Lỗi Phổ Biến Trên Theme Woodmart (Woodmart Theme)

### 2.0. Danh sách các Module cần TẮT trong WC Enhancement Kit khi dùng Woodmart

Khi sử dụng Woodmart, để tránh xung đột giao diện và mã nguồn, bạn cần tắt (Disable) các module sau trong cấu hình của plugin **WC Enhancement Kit**:

| Tên Module (WC Enhancement Kit)    | Lý do phải tắt                                                                                                                         | Tính năng thay thế tương đương của Woodmart / Hướng xử lý                                                                               |
| :---------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Quick Purchase & AJAX**     | Gây lỗi hiển thị lệch nút mua hàng, xung đột CSS do Woodmart sử dụng cấu trúc DOM khác biệt.                               | Sử dụng tính năng **Buy Now** và AJAX Add to Cart mặc định cực kỳ tối ưu của Woodmart.                                           |
| **Custom Checkout**           | Tránh xung đột xử lý các trường thanh toán (Checkout Fields) do Woodmart sử dụng hệ thống layouts riêng cho trang Checkout. | Tùy biến thông qua**Woodmart Layouts** (Woodmart -> Layouts -> Checkout) hoặc cài đặt chuyên sâu của theme.                          |
| **Pagination**                | Gây lỗi định dạng phân trang, làm méo mó các nút chuyển trang hoặc mất kiểu dáng mặc định của Woodmart.               | Sử dụng tính năng phân trang gốc của Woodmart (hỗ trợ phân trang số, Infinite Scroll, hoặc nút Load More).                              |
| **CDN Optimizer**             | Tránh xung đột tải tài nguyên tĩnh (fonts, icons, CSS/JS) và lỗi CORS do Woodmart đã tối ưu hóa hiệu năng rất sâu.      | Sử dụng công cụ tối ưu hiệu năng tích hợp sẵn của Woodmart tại**Theme Settings -> Performance**.                                  |
| **Product Tabs** (Tùy chọn) | Có thể tắt nếu muốn tinh gọn trang sản phẩm và sử dụng trình quản lý Tab mặc định của theme.                            | Cấu hình Custom Tabs trực tiếp của Woodmart tại**Theme Settings -> Single Product -> Tabs** hoặc thông qua **Woodmart Layouts**. |

---

### 2.1. Lỗi: Ảnh bị mất sau một thời gian hoặc không hiển thị khi dùng Domain Aliases

* **Triệu chứng**:
  * Website hoạt động bình thường nhưng sau một thời gian, hình ảnh đột ngột bị mất liên kết hiển thị.
  * Hoặc khi sử dụng cấu hình đa tên miền trỏ về một mã nguồn (Domain Aliases), hình ảnh chỉ hiển thị ở tên miền chính, các tên miền khác bị lỗi không hiển thị hình ảnh.
* **Nguyên nhân**: Do cơ chế lưu cache CSS của Elementor biên dịch đường dẫn ảnh thành liên kết tuyệt đối (có chứa domain chính) và lưu vào file tĩnh. Khi truy cập qua domain phụ hoặc sau một thời gian cache hết hạn, trình duyệt sẽ chặn hoặc không tìm thấy ảnh.
* **Cách khắc phục**:
  1. Truy cập **Dashboard -> Elementor -> Settings -> Performance** (hoặc tab **Advanced** tùy phiên bản).
  2. Tìm đến tính năng quản lý cache CSS và chọn **Disable** (Vô hiệu hóa cache).
  3. Vào **Elementor -> Tools** và nhấn nút **Regenerate Files & Data** để làm sạch bộ nhớ cache CSS cũ.

### 2.2. Lỗi: Menu quá dài đẩy giao diện tạo khoảng trống trắng vô lý ở các trang ngắn

* **Triệu chứng**: Khi truy cập vào các trang có nội dung ngắn (như trang liên hệ, trang giỏ hàng trống hoặc Landing Page ngắn), giao diện xuất hiện khoảng trống trắng rất lớn và vô lý ở phía dưới footer, khiến layout trang bị kéo giãn quá dài.
* **Nguyên nhân**: Thiết lập thanh menu dọc (Vertical Menu) hoặc danh mục sản phẩm của Woodmart có quá nhiều mục con xếp dọc. Khi chiều cao của menu vượt quá chiều cao nội dung trang, nó sẽ đẩy footer xuống dưới cùng để tương thích, tạo ra khoảng trống trắng thừa.
* **Cách khắc phục**: Tách biệt hệ thống menu thành hai luồng riêng cho Desktop và Mobile:
  1. **Trên Desktop**: Sử dụng giải pháp **HTML Blocks** trong Woodmart để thiết kế **Mega Menu** dàn theo hàng ngang (Grid columns) thay vì xếp dọc dài.
     - Tạo một HTML Block mới tại **Dashboard -> HTML Blocks -> Add New** và dựng giao diện menu chia cột.
     - Gán HTML Block này vào menu cha trong mục **Appearance -> Menus** (sử dụng tùy chọn thiết lập Mega Menu của Woodmart).
  2. **Trên Mobile**: Dựng menu dạng cây danh mục lồng nhau (Dropdown/Accordion dọc) như cũ để người dùng dễ cuộn vuốt bằng ngón tay.
  3. **Kết luận**: Cần duy trì **2 menu riêng biệt** phục vụ cho mục đích hiển thị khác nhau trên Desktop và Mobile trong cấu hình Header Builder của Woodmart.

### 2.3. Lỗi thuộc tính không hiển thị dạng Swatches hoặc cấu hình không lên dạng ô chọn

* **Triệu chứng**: Các thuộc tính sản phẩm (như Kích thước, Màu sắc, Phân loại...) hiển thị dưới dạng danh sách thả xuống (Dropdown) mặc định của WooCommerce thay vì các ô chọn Swatches trực quan.
* **Nguyên nhân**: Woodmart yêu cầu phải kích hoạt thủ công tính năng hiển thị Swatch ở cả cấp độ thuộc tính (Attribute) và cấp độ giá trị thuộc tính (Term).
* **Cách khắc phục**:
  1. **Cấu hình cấp Thuộc tính**:
     - Truy cập **Products -> Attributes**, tìm thuộc tính cần cấu hình (ví dụ: `Custom` hoặc `Size`) và nhấn **Edit**.
     - Thiết lập các tùy chọn hiển thị: **Swatch style** (chọn Text, Color hoặc Image), **Disabled swatch style** (kiểu hiển thị khi hết hàng), **Swatch shape** (tròn hoặc vuông), và **Swatch size**. Nhấn **Update** để lưu.
  2. **Cấu hình cấp Giá trị (Term)**:
     - Quay lại bảng thuộc tính, click vào liên kết **Configure terms** của thuộc tính vừa chỉnh sửa.
     - Nhấn **Edit** vào từng giá trị (ví dụ với thuộc tính `Custom` có các term là `Yes` và `No`, bạn cần edit các term này) và tích bật tùy chọn hiển thị tương ứng (ví dụ: **Text swatch**).
  3. **Mẹo tối ưu thời gian cấu hình (Quan trọng)**:
     - **Không cần phải cấu hình bật thủ công cho toàn bộ các term** trong danh sách. Woodmart có cơ chế: **Chỉ cần có ít nhất 1 term trong danh sách thuộc tính được bật cấu hình Swatch**, thì tất cả các term còn lại của thuộc tính đó sẽ tự động được hiển thị ra ngoài Frontend dưới dạng Swatch.
     - *Ví dụ*: Thuộc tính `Size` gồm các term `S, M, L, XL`. Bạn chỉ cần chọn một term thường xuyên được sử dụng (ví dụ: `L`), nhấn **Edit** và bật **Text swatch** lên là đủ. Hệ thống sẽ tự động hiển thị các term còn lại (`S`, `M`, `XL`) dưới dạng Swatch ngoài trang cửa hàng.

### 2.4. Lỗi Elementor không load được hoặc báo lỗi Safe Mode (nếu dùng Elementor)

* **Triệu chứng**: Khi nhấn chỉnh sửa trang bằng Elementor, trình soạn thảo bị kẹt hoặc yêu cầu kích hoạt chế độ an toàn (Safe Mode).
* **Nguyên nhân**: Woodmart tích hợp rất nhiều widget và tính năng nâng cao. Nếu server/hosting có cấu hình thấp, Elementor sẽ bị cạn kiệt tài nguyên xử lý.
* **Cách khắc phục**:
  1. Tăng thông số `Memory limit in MB` lên ít nhất `256M` hoặc `512M` trong tab quản lý **PHP** của **Ploi**.
  2. Truy cập **Woodmart** -> **Theme Settings** -> **Performance** -> **Plugins**: Tắt bớt các tính năng/thư viện của Woodmart không sử dụng để giảm tải tài nguyên hệ thống.

### 2.5. Lỗi bộ lọc bên Sidebar (Filter) bị mất tác dụng hoặc không chạy khi chuyển trang

* **Triệu chứng**: Khi click chọn bộ lọc (lọc giá, lọc thuộc tính màu sắc) ở sidebar trang cửa hàng, trang web load AJAX nhưng không lọc được sản phẩm, hoặc sau khi chuyển trang 2 bộ lọc biến mất.
* **Nguyên nhân**: Tính năng tải trang bằng AJAX của Woodmart (AJAX Shop) bị xung đột với các plugin tạo bộ lọc nâng cao bên thứ ba.
* **Cách khắc phục**:
  1. Truy cập **Woodmart** -> **Theme Settings** -> **Shop** -> **Shop page**.
  2. Cuộn xuống mục **AJAX shop** và chọn **Disable** (Tắt).
  3. Lưu lại thiết lập. Lúc này bộ lọc sẽ tải lại trang truyền thống hoặc sử dụng JS của plugin lọc một cách ổn định.

### 2.6. Lỗi mất header hoặc các element trên header sau khi di chuyển qua lại desktop và mobile

* **Triệu chứng**: Khi xem website bằng thiết bị di động (Mobile), thanh Header hoặc một số phần tử trên Header (như logo, menu, giỏ hàng) bị biến mất hoàn toàn, trong khi trên máy tính (Desktop) vẫn hiển thị bình thường và ngược lại.
* **Nguyên nhân**: Do tính năng tối ưu hóa DOM trên Mobile (Mobile DOM optimization) của Woodmart lưu cache sai cấu trúc giao diện hoặc lọc bỏ nhầm các thẻ HTML trên thiết bị di động để cải thiện điểm số tốc độ tải trang (chỉ cache được một màn hình cố định).
* **Cách khắc phục**:
  1. Truy cập **Woodmart -> Theme Settings -> Performance -> Other**.
  2. Tìm tùy chọn **Mobile DOM optimization** và chuyển sang trạng thái **Disable** (Tắt).
  3. Nhấn lưu lại thiết lập và tiến hành làm sạch bộ nhớ cache của website.

### 2.7. Lỗi: Hiển thị các biến thể (Variants) như là sản phẩm riêng lẻ gây trùng lặp sản phẩm (Duplicate Products)

* **Triệu chứng**: Trên trang cửa hàng hoặc danh sách sản phẩm, các biến thể của cùng một sản phẩm (ví dụ: các kích thước, màu sắc khác nhau) hiển thị dưới dạng các sản phẩm độc lập. Điều này gây ra tình trạng trùng lặp sản phẩm hàng loạt khiến khách hàng thấy hiển thị quá nhiều sản phẩm giống nhau.
* **Nguyên nhân**: Do tùy chọn hiển thị biến thể riêng lẻ (Variation as product) đang được kích hoạt trong phần cấu hình của theme Woodmart.
* **Cách khắc phục**:
  1. Truy cập **Dashboard -> Woodmart -> Theme Settings -> Shop -> Variable products**.
  2. Tìm đến mục **Variation as product** -> tùy chọn **Show single variation**.
  3. Tiến hành **Tắt** (Vô hiệu hóa) tùy chọn này để chỉ hiển thị sản phẩm cha duy nhất.
  4. Nhấn lưu cài đặt và xóa cache trang web để kiểm tra lại kết quả.

---

## 3. Các Vấn Đề Tương Thích & Xung Đột Giữa 2 Theme Với Plugin Bổ Trợ

### 3.1. Tránh bật module trùng lặp tính năng

* **Woodmart**: Đã tích hợp sẵn *Quick View*, *Compare*, *Wishlist*, *Buy Now*, *Swatches*, *Custom Pagination*. Do đó, khi cài đặt thêm các plugin đa năng (như WC Enhancement Kit), bạn **phải tắt** các module này trong plugin để tránh lỗi xung đột CSS/JS.
* **Flatsome**: Không tích hợp sẵn Swatches cho sản phẩm biến thể ở trang danh mục và cơ chế AJAX Cart cho sản phẩm biến thể. Vì vậy, bạn **nên bật** các module bổ trợ của plugin như *Quick Purchase & AJAX Setting* và *Variation Display*.

---

## 4. Các Lỗi Phổ Biến Trên WordPress (WordPress Common Issues)

### 4.1. Lỗi: Bị kẹt hoặc chặn ngoài trang đăng nhập (Blocked Login Page)

* **Triệu chứng**: Khi cố gắng truy cập trang quản trị `/wp-admin` hoặc `/wp-login.php`, bạn bị từ chối truy cập (Access Denied), chuyển hướng hoặc báo lỗi đăng nhập ngay cả khi nhập đúng tài khoản/mật khẩu.
* **Nguyên nhân**: Tính năng chặn đăng nhập bằng mật khẩu truyền thống (**Disable Password Login**) đang hoạt động (do cấu hình bảo mật hoặc sau khi clone website từ bản backup cũ đã bật sẵn tùy chọn này).
* **Cách khắc phục**:
  1. Sử dụng FileZilla hoặc phần mềm SFTP để kết nối vào mã nguồn website trên máy chủ.
  2. Truy cập theo đường dẫn thư mục: `wp-content/plugins/wc-enhancement-kit/modules/admin-util/`.
  3. Mở file [admin-util.php](<file:///F:/tech/tài%20liệu/plugin/wc-enhancement-kit/modules/admin-util/admin-util.php>) bằng trình soạn thảo mã nguồn.
  4. Tìm đến dòng `87` và tiến hành comment lại dòng khởi tạo bộ lọc bảo mật:
     ```php
     // Security_Filters_Core::instance()->init();
     ```
  5. Lưu lại và tải đè file lên server để tạm thời vô hiệu hóa bộ lọc bảo mật này.
  6. Tiến hành tải lại trang đăng nhập và đăng nhập bình thường bằng tài khoản mật khẩu.
  7. Sau khi đăng nhập thành công, nếu cần bật lại cơ chế bảo mật đăng nhập qua Google, hãy hoàn tất thiết lập Google OAuth (trong Nextend Social Login) rồi mở lại file [admin-util.php](<file:///F:/tech/tài%20liệu/plugin/wc-enhancement-kit/modules/admin-util/admin-util.php>) và xóa ký tự comment `//` ở dòng `87` để kích hoạt lại tính năng chặn.

### 4.2. Lỗi: Các đường dẫn trang con, sản phẩm hoặc bộ sưu tập (Collection) gặp lỗi 404 Not Found

* **Triệu chứng**: Sau khi di chuyển website (Migration), thay đổi tên miền hoặc nhân bản (Clone) site, bạn chỉ có thể truy cập được trang chủ, trong khi tất cả các trang con, danh mục sản phẩm, bộ sưu tập hoặc bài viết đều báo lỗi 404.
* **Nguyên nhân**: Do các quy tắc rewrite đường dẫn (Rewrite Rules) trong cơ sở dữ liệu hoặc file cấu hình `.htaccess`/Nginx chưa được làm mới để tương thích với tên miền mới.
* **Cách khắc phục**:
  1. Đăng nhập vào trang quản trị WordPress Admin của bạn.
  2. Truy cập vào menu **Settings (Cài đặt) -> Permalinks (Đường dẫn tĩnh)**.
  3. Giữ nguyên cấu hình hiện tại (không cần chỉnh sửa gì thêm), cuộn xuống dưới cùng và nhấn nút **Save Changes (Lưu thay đổi)**.
  4. Thao tác này sẽ tự động ra lệnh cho WordPress làm sạch bộ nhớ đệm và viết lại (Flush Rewrite Rules) cấu trúc liên kết tĩnh mới cho toàn bộ các trang con trên hệ thống.

### 4.3. Lỗi: Giao diện quản trị Admin hiển thị sai ngôn ngữ mong muốn (Admin Language Mismatch)

* **Triệu chứng**: Khi thay đổi ngôn ngữ hiển thị chính của website (ví dụ sang tiếng Đức, tiếng Tây Ban Nha), giao diện trang quản trị Admin của bạn cũng tự động chuyển sang ngôn ngữ đó, gây khó khăn cho việc quản trị bằng tiếng Anh.
* **Nguyên nhân**: Theo mặc định, WordPress sẽ áp dụng ngôn ngữ chính của site cho cả phần Frontend và Backend. Tuy nhiên, WordPress hỗ trợ cơ chế cho phép cấu hình ngôn ngữ của Frontend và Backend độc lập theo từng tài khoản người dùng.
* **Cách khắc phục**:
  Để chuyển riêng giao diện quản trị Admin về tiếng Anh (hoặc ngôn ngữ mong muốn khác) mà không ảnh hưởng đến ngôn ngữ hiển thị của khách hàng ngoài trang chủ:
  1. Đăng nhập vào trang quản trị WordPress Admin.
  2. Truy cập menu **Users -> Profile**.
  3. Tìm đến tùy chọn **Language**.
  4. Chọn ngôn ngữ mong muốn sử dụng cho trang quản trị (ví dụ: `English (United States)`).
  5. Cuộn xuống dưới cùng và nhấn nút **Update Profile** để lưu lại thiết lập.

### 4.4. Lỗi: Giao diện khách (Incognito / Logged-out) bị vỡ CSS/JS sau khi xóa cache WP Rocket nhưng giao diện Admin không bị

* **Triệu chứng**: Sau khi quản trị viên thực hiện xóa cache (Clear cache) trong plugin WP Rocket, giao diện hiển thị cho khách hàng (hoặc khi truy cập bằng tab ẩn danh không đăng nhập) bị vỡ bố cục, lỗi hiển thị CSS hoặc các hiệu ứng JS không hoạt động. Trong khi đó, nếu đăng nhập tài khoản Admin thì mọi thứ vẫn hiển thị bình thường, không xảy ra lỗi.
* **Nguyên nhân**: WP Rocket khi xóa cache sẽ tạo ra các tệp tối ưu hóa CSS/JS tĩnh mới với tên tệp (hash name) mới. Tuy nhiên, bộ nhớ đệm phía máy chủ **FastCGI Cache** (đang chạy trên hệ thống Nginx của Ploi) vẫn lưu giữ nội dung HTML cũ (đang tham chiếu đến các tệp CSS/JS cũ đã bị WP Rocket xóa bỏ). Do đó, khách vãng lai (không đăng nhập) truy cập sẽ nhận cache HTML cũ từ FastCGI và bị lỗi tải CSS/JS. Giao diện Admin không bị lỗi là do hệ thống mặc định cấu hình bỏ qua FastCGI Cache cho người dùng đã đăng nhập.
* **Cách khắc phục**:
  Bạn có thể chọn một trong hai phương án sau để làm sạch bộ nhớ đệm:
  * **Phương án 1 (Tự động)**: Chờ trong vòng `60 phút`. Hệ thống FastCGI Cache được cấu hình mặc định tự động hết hạn và làm mới lại sau mỗi 60 phút.
  * **Phương án 2 (Thủ công - Tức thì)**: Thực hiện dọn dẹp trực tiếp trên bảng điều khiển Ploi:
    1. Đăng nhập vào tài khoản quản trị **Ploi.io**.
    2. Chọn Server và đi tới **Domain** (Website đang bị lỗi).
    3. Truy cập vào menu **Manage -> FastCGI Cache**.
    4. Nhấp vào nút **Flush** (hoặc Clear Cache) để ép buộc máy chủ xóa sạch bộ nhớ đệm FastCGI ngay lập tức. Giao diện khách hàng sẽ hiển thị bình thường trở lại ngay sau đó.

### 4.5. Lỗi: Email hệ thống gửi đi bị trống nội dung (Blank/Empty Emails)

* **Triệu chứng**: Khi khách hàng đặt hàng hoặc hệ thống gửi các email thông báo (như New Order, Processing Order...), email vẫn gửi thành công nhưng phần nội dung bên trong thư hoàn toàn trống trơn (trắng trang).
* **Nguyên nhân**: Do plugin tùy biến mẫu email **YayMail - WooCommerce Email Customizer** đang được kích hoạt trên site nhưng các mẫu email bên trong nó chưa từng được thiết lập, cấu hình hoặc lưu dữ liệu (chưa kéo thả nội dung). Khi đó, YayMail sẽ ghi đè lên các mẫu email mặc định của WooCommerce và gửi đi các template trống.
* **Cách khắc phục**:
  Bạn có thể xử lý lỗi này bằng một trong hai phương án sau:
  * **Phương án 1 (Nhanh nhất)**: Nếu không có nhu cầu tùy biến giao diện email phức tạp, hãy truy cập vào **Plugins -> Installed Plugins** và tiến hành **Deactivate (Vô hiệu hóa)** plugin **YayMail**. Hệ thống sẽ tự động khôi phục và sử dụng lại các mẫu email mặc định chuẩn của WooCommerce.
  * **Phương án 2 (Cấu hình thủ công)**: Nếu muốn giữ plugin để thiết kế email:
    1. Truy cập **WooCommerce -> Email Customizer** (hoặc vào **YayMail** từ thanh menu chính).
    2. Chọn từng mẫu email (ví dụ: *New Order, Processing Order...*) trong danh mục dropdown ở góc trên.
    3. Tiến hành thiết kế, thêm thắt nội dung, logo, thông tin đơn hàng bằng trình kéo thả của YayMail.
    4. Nhấn **Save** cho từng mẫu email để hệ thống lưu cấu hình và gửi thư có nội dung chính xác.

### 4.6. Lỗi: Plugin Upsell không hỗ trợ hoặc không có tùy chọn lọc theo Collection hoặc EC Product Type

* **Triệu chứng**: Khi cấu hình các chiến dịch Upsell (Bán thêm/Bán kèm sản phẩm), hệ thống không hiển thị tùy chọn lọc hoặc kích hoạt chiến dịch dựa trên **Collection** (Bộ sưu tập) hoặc **EC Product Type** (Phân loại loại sản phẩm).
* **Nguyên nhân**: Bản cài đặt mặc định/tiêu chuẩn của plugin **UpSell WP** không hỗ trợ các cấu trúc phân loại tự tùy biến (Custom Taxonomies) như Collection (`wcek_collection`) hay EC Product Type (`ec_product_type`).
* **Cách khắc phục**:
  Do công ty đã mua và kích hoạt bản quyền **Pro** của UpSell WP, hoàn toàn có thể kích hoạt add-on đi kèm để mở khóa tính năng này:
  1. Đăng nhập vào trang quản trị WordPress.
  2. Truy cập vào menu **UpSell WP -> Add On**.
  3. Tìm kiếm add-on có tên **Custom Taxonomy Addon**.
  4. Nhấn nút tải về (Download) và tiến hành cài đặt, kích hoạt (Activate) add-on này giống như một plugin thông thường.
  5. Sau khi kích hoạt thành công, các tùy chọn phân loại theo Collection và EC Product Type sẽ tự động xuất hiện đầy đủ trong phần thiết lập điều kiện của chiến dịch Upsell.
