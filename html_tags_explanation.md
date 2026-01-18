# Giải Thích Toàn Bộ Dự Án (HTML & Cấu Trúc)

Dưới đây là giải thích chi tiết về cấu trúc và các thẻ HTML đã được sử dụng trong dự án "Thế Giới Động Vật", giúp bạn chuẩn bị cho bài thuyết trình.

## 1. Cấu Trúc Thư Mục

Dự án được tổ chức một cách rõ ràng để dễ dàng quản lý:

-   **/ (Thư mục gốc)**: Chứa các trang chính và các file quan trọng.
    -   `index.html`: Trang chủ của website.
    -   `members.html`: Trang giới thiệu thành viên.
    -   `contact.html`: Trang liên hệ với form.
    -   `tren_can.html`, `duoi_bien.html`: Các trang con hiển thị các loài động vật được phân loại.
    -   `style.css`: File CSS chính cho trang chủ và các trang phân loại.
    -   `README.md`: File giới thiệu dự án.
-   **/animals/**: Chứa các trang chi tiết cho từng loài động vật.
    -   `lion.html`, `tiger.html`, v.v.
-   **/pic/**: Chứa tất cả các hình ảnh được sử dụng trong dự án.
-   **/video/**: Chứa các file video.

**Kỹ thuật đã dùng**:
-   **Tổ chức file theo chức năng**: Các trang HTML chính ở thư mục gốc, các trang chi tiết động vật được gom vào thư mục `animals`, hình ảnh và video cũng có thư mục riêng. Đây là một cách làm phổ biến để giữ cho dự án gọn gàng.

## 2. Giải Thích Các Thẻ HTML Đã Dùng

Chúng ta sẽ phân tích các thẻ HTML được sử dụng trong các trang chính.

### Trong `index.html` (Trang chủ)

-   `<!DOCTYPE html>`: Khai báo đây là một tài liệu HTML5.
-   `<html lang="vi">`: Thẻ gốc của tài liệu, `lang="vi"` chỉ định ngôn ngữ của trang là Tiếng Việt, tốt cho SEO và các công cụ hỗ trợ.
-   `<head>`: Chứa các thông tin meta về trang web.
    -   `<meta charset="UTF-8">`: Khai báo bộ mã ký tự là UTF-8 để hiển thị đúng Tiếng Việt.
    -   `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: **Kỹ thuật Responsive Design**. Thẻ này rất quan trọng, giúp trang web hiển thị tốt trên các thiết bị khác nhau (di động, máy tính bảng) bằng cách điều chỉnh chiều rộng trang theo chiều rộng thiết bị.
    -   `<title>`: Đặt tiêu đề cho tab của trình duyệt.
    -   `<link rel="stylesheet" href="style.css">`: Liên kết đến file CSS bên ngoài để định dạng cho trang.
-   `<body>`: Chứa toàn bộ nội dung hiển thị của trang web.
    -   `<img class="header-banner">`: Hiển thị ảnh banner ở đầu trang.
    -   `<header>`: Thẻ ngữ nghĩa, định nghĩa phần đầu của trang, thường chứa logo, tiêu đề, và thanh điều hướng.
    -   `<h1>`: Thẻ tiêu đề cấp 1, thường là tiêu đề chính của trang.
    -   `<ul>` (Unordered List): Dùng để tạo danh sách không có thứ tự.
    -   `<li>` (List Item): Mỗi mục trong danh sách.
    -   `<a>` (Anchor): Thẻ liên kết.
        -   `href="index.html"`: Liên kết đến một trang khác.
        -   `href="#animal-grid"`: Liên kết đến một phần tử có `id="animal-grid"` trong cùng một trang (tạo hiệu ứng cuộn trang).
        -   `target="_blank"`: Mở liên kết trong một tab hoặc cửa sổ mới.
    -   `<main>`: Thẻ ngữ nghĩa, chứa nội dung chính của trang.
    -   `<section>`: Thẻ ngữ nghĩa, dùng để nhóm các nội dung có liên quan với nhau.
    -   `<article>`: Thẻ ngữ nghĩa, định nghĩa một mẩu nội dung độc lập, có thể tự nó tồn tại (ví dụ: một bài post, một thẻ sản phẩm).
    -   `<h2>`, `<h3>`: Các thẻ tiêu đề phụ, giúp phân cấp nội dung.
    -   `<p>`: Thẻ đoạn văn.
    -   `<video controls>`:
        -   `<video>`: Nhúng một video vào trang.
        -   `controls`: Thuộc tính cho phép hiển thị các nút điều khiển video (play, pause, âm lượng).
        -   `<source src="..." type="...">`: Chỉ định nguồn và định dạng của video.
    -   `<footer>`: Thẻ ngữ nghĩa, định nghĩa phần chân trang.

### Trong `contact.html` (Trang Liên hệ)

Trang này sử dụng các thẻ form để thu thập thông tin người dùng:

-   `<form action="#" method="POST">`:
    -   `<form>`: Thẻ bao bọc một biểu mẫu.
    -   `action="#"`: Nơi dữ liệu sẽ được gửi đến (ở đây là `#` nghĩa là không gửi đi đâu cả).
    -   `method="POST"`: Phương thức gửi dữ liệu.
-   `<label for="...">`: Nhãn cho một trường nhập liệu. `for` sẽ liên kết với `id` của trường.
-   `<input>`: Thẻ nhập liệu đa năng.
    -   `type="text"`: Nhập văn bản.
    -   `type="email"`: Nhập email (trình duyệt sẽ kiểm tra định dạng).
    -   `type="radio"`: Nút chọn một trong nhiều lựa chọn. Các `input` có cùng `name` sẽ thuộc một nhóm.
    -   `type="checkbox"`: Nút chọn có thể chọn hoặc không.
-   `<textarea>`: Trường nhập văn bản nhiều dòng.
-   `<button type="submit">`: Nút để gửi form.

### Trong `members.html` (Trang Thành viên)

Trang này sử dụng bảng để hiển thị danh sách:

-   `<table>`: Thẻ chính để tạo một bảng.
-   `<thead>`: Nhóm phần tiêu đề của bảng.
-   `<tbody>`: Nhóm phần thân của bảng.
-   `<tr>` (Table Row): Một hàng trong bảng.
-   `<th>` (Table Header): Một ô tiêu đề trong hàng.
-   `<td>` (Table Data): Một ô dữ liệu trong hàng.
    -   `data-label="..."`: Một thuộc tính dữ liệu tùy chỉnh. **Kỹ thuật Responsive Table**: Thuộc tính này được dùng trong CSS để tạo bảng hiển thị tốt trên di động, biến các hàng thành các khối riêng biệt và dùng `::before` để hiển thị lại tiêu đề cột.

### Trong `animals/lion.html` (Trang Chi tiết)

-   `colspan="2"`: Thuộc tính của `<td>` hoặc `<th>`, cho phép một ô kéo dài (gộp) qua nhiều cột.
-   Cấu trúc trang này sử dụng `<table>` để dàn layout (chia cột hình ảnh và văn bản). Đây là một kỹ thuật cũ, ngày nay người ta thường dùng CSS Flexbox hoặc Grid để dàn layout vì linh hoạt hơn. Tuy nhiên, với nội dung đơn giản thì nó vẫn hoạt động tốt.

Chúc bạn có một bài thuyết trình thành công!