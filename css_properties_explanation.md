# Giải Thích Toàn Bộ Dự Án (CSS & Kỹ Thuật Styling)

Dưới đây là giải thích chi tiết về các thuộc tính và kỹ thuật CSS đã được sử dụng trong dự án "Thế Giới Động Vật".

## 1. Cách Tổ Chức CSS

Dự án sử dụng hai cách tiếp cận để viết CSS:

1.  **CSS Ngoài (External CSS)**:
    -   File `style.css` được liên kết vào `index.html` và các trang phân loại (`tren_can.html`, `duoi_bien.html`).
    -   **Ưu điểm**: Giúp tái sử dụng code CSS cho nhiều trang, dễ bảo trì và quản lý tập trung. Khi cần thay đổi giao diện chung, chỉ cần sửa một file.
2.  **CSS Trong (Internal CSS)**:
    -   Các trang `members.html`, `contact.html`, và các trang chi tiết động vật (ví dụ `animals/lion.html`) sử dụng thẻ `<style>` ngay trong file HTML.
    -   **Ưu điểm**: Giúp CSS của một trang cụ thể độc lập hoàn toàn, không bị ảnh hưởng bởi file CSS chung. Điều này hữu ích cho các trang có layout đặc thù.
    -   **Nhược điểm**: Không tái sử dụng được, nếu nhiều trang có style giống nhau thì phải copy-paste code.

**Tại sao lại dùng cả hai cách?**
Đây có thể là một lựa chọn thiết kế: trang chủ có một giao diện chung, trong khi các trang phụ (thành viên, liên hệ) có thiết kế đơn giản và độc lập hơn nên không cần dùng file CSS chung.

## 2. Giải Thích Các Thuộc Tính CSS và Kỹ Thuật

Chúng ta sẽ phân tích các đoạn code trong `style.css` (file CSS chính).

### Layout và Định Vị (Layout & Positioning)

-   **CSS Box Model**:
    -   `margin`: Tạo khoảng trống *bên ngoài* một phần tử.
    -   `padding`: Tạo khoảng trống *bên trong* một phần tử, giữa nội dung và viền.
    -   `border`: Đường viền của phần tử.
-   `display`: Thuộc tính quan trọng nhất để kiểm soát layout.
    -   `display: block`: Phần tử chiếm toàn bộ chiều rộng có sẵn, các phần tử sau sẽ nằm ở hàng mới (ví dụ: `<h1>`, `<p>`, `<div>`).
    -   `display: inline-block`: Phần tử nằm trên cùng một hàng với các phần tử khác, nhưng có thể đặt `width` và `height` (ví dụ: các nút bấm).
    -   `display: flex`: **Kỹ thuật Flexbox**. Dùng cho `.main-nav-list` để sắp xếp các mục menu nằm ngang và căn giữa. `justify-content: center` để căn giữa các mục theo chiều ngang, `gap` để tạo khoảng cách giữa chúng.
    -   `display: grid`: **Kỹ thuật CSS Grid**. Dùng cho `.animal-grid` để tạo một lưới các thẻ động vật.
        -   `grid-template-columns: repeat(auto-fill, minmax(280px, 1fr))`: Đây là một kỹ thuật **responsive grid** rất mạnh. Nó tự động tạo ra các cột có chiều rộng tối thiểu là `280px`. Nếu còn thừa không gian, nó sẽ tự động lấp đầy (`auto-fill`) và chia đều không gian còn lại cho các cột (`1fr`). Khi không gian màn hình thu hẹp, các thẻ sẽ tự động xuống hàng.
-   `position`:
    -   Trong `members.html`, thuộc tính `position: relative` và `position: absolute` được dùng để tùy chỉnh lại bảng trên di động. `<td>` được đặt là `relative`, và `::before` pseudo-element được đặt là `absolute` để hiển thị lại tiêu đề cột.

### Typography (Chữ Viết)

-   `font-family`: Chọn font chữ cho văn bản.
-   `font-size`: Kích thước chữ.
-   `font-weight`: Độ đậm của chữ (ví dụ: `600` là semi-bold, `700` là bold, `900` là black).
-   `color`: Màu chữ.
-   `line-height`: Chiều cao của một dòng văn bản, giúp tăng/giảm khoảng cách giữa các dòng để dễ đọc hơn.
-   `text-align`: Căn lề văn bản (trái, phải, giữa).
-   `text-decoration: none`: Xóa gạch chân mặc định của thẻ `<a>`.

### Màu Sắc và Nền (Colors & Background)

-   `background-color`: Đặt màu nền cho một phần tử.
-   `box-shadow`: Tạo hiệu ứng đổ bóng cho một phần tử (ví dụ: trên các thẻ `.animal-card`), tạo cảm giác chiều sâu.

### Hình Ảnh và Video

-   `object-fit: cover`: Dùng cho `.header-banner` và ảnh thẻ động vật. Khi kích thước của ảnh không khớp với kích thước của vùng chứa, thuộc tính này sẽ cắt ảnh để lấp đầy vùng chứa mà không làm méo ảnh.
-   `aspect-ratio: 1 / 1`: Giữ cho tỷ lệ khung hình của ảnh là 1:1 (hình vuông), giúp các thẻ trong lưới có kích thước đồng đều.
-   `border-radius`: Bo tròn các góc của một phần tử, tạo ra giao diện mềm mại hơn.

### Hiệu Ứng và Tương Tác (Effects & Interaction)

-   `:hover`: Một "pseudo-class", cho phép định nghĩa style cho một phần tử khi người dùng di chuột lên nó.
    -   Ví dụ: `.animal-card:hover` sẽ thay đổi `transform` và `box-shadow` để tạo hiệu ứng "nổi" lên, thu hút sự chú ý.
-   `transition`: Tạo hiệu ứng chuyển cảnh mượt mà khi một thuộc tính CSS thay đổi.
    -   Ví dụ: `transition: transform 0.2s ease, box-shadow 0.2s ease` làm cho hiệu ứng `:hover` trên `.animal-card` diễn ra mượt mà trong 0.2 giây.
-   `cursor: pointer`: Biến con trỏ chuột thành hình bàn tay khi di chuột qua một phần tử, cho người dùng biết rằng họ có thể nhấp vào đó.

### Kỹ Thuật Responsive Design

-   **`@media` Query**: Đây là nền tảng của responsive design trong CSS. Nó cho phép áp dụng các đoạn CSS khác nhau tùy thuộc vào điều kiện của thiết bị (thường là chiều rộng màn hình).
-   **Ví dụ trong `members.html`**:
    ```css
    @media (max-width: 768px) {
        /* CSS cho màn hình có chiều rộng tối đa là 768px (máy tính bảng, di động) */
        .members-table, .members-table tr, .members-table td {
            display: block; /* Biến các ô trong bảng thành các khối riêng biệt */
        }
        /* ... các style khác để biến bảng thành danh sách dọc */
    }
    ```
-   **Mobile-First vs. Desktop-First**: Dự án này dường như sử dụng cách tiếp cận **Desktop-First**, tức là viết CSS cho màn hình lớn trước, sau đó dùng `@media (max-width: ...)` để điều chỉnh cho màn hình nhỏ hơn.

Chúc bạn có một bài thuyết trình thành công!