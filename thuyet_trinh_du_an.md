# Thuyết trình Dự án Trang web Động vật

## 1. Tóm tắt chung về dự án

Đây là một dự án trang web tĩnh (static website) đơn giản, được thiết kế để giới thiệu thông tin về các loài động vật khác nhau. Trang web này có các thành phần chính sau:

*   **Trang chủ (`index.html`):** Là điểm truy cập chính, có thể liệt kê các danh mục động vật hoặc giới thiệu một loài động vật nổi bật.
*   **Các trang chi tiết động vật (`animals/*.html`):** Mỗi loài động vật có một trang riêng, cung cấp mô tả chi tiết, hình ảnh và âm thanh/video minh họa.
*   **Tạo kiểu (`style.css`):** Giao diện và bố cục của trang web được kiểm soát hoàn toàn bởi một file CSS duy nhất.
*   **Tích hợp đa phương tiện:** Sử dụng các file âm thanh và video để tăng tính sinh động cho các trang chi tiết động vật.
*   **Các file phụ trợ:** Có thêm một số file HTML phụ (`duoi_bien.html`, `tren_can.html`, v.v.) và các file Markdown (`.md`) dùng để giải thích hoặc tài liệu.

Mục tiêu chính của dự án là trình bày thông tin một cách rõ ràng, trực quan, có thêm các yếu tố đa phương tiện để thu hút người xem.

## 1.1 Cấu trúc thư mục và vai trò các file

Dự án được tổ chức thành các thư mục rõ ràng, mỗi thư mục có một vai trò cụ thể:

*   **`/` (Thư mục gốc của dự án):**
    *   `index.html`: Trang chủ của trang web.
    *   `contact.html`: Trang liên hệ.
    *   `members.html`: Trang giới thiệu thành viên.
    *   `duoi_bien.html`: Trang về động vật dưới biển.
    *   `tren_can.html`: Trang về động vật trên cạn.
    *   `dong_vat_an_thuc_vat.html`: Trang về động vật ăn thực vật.
    *   `loai_an_thit.html`: Trang về động vật ăn thịt.
    *   `style.css`: File CSS chính chứa toàn bộ các quy tắc tạo kiểu cho trang web.
    *   `README.md`: File hướng dẫn hoặc thông tin tổng quan về dự án.
    *   `html_tags_explanation.md`: File Markdown giải thích các thẻ HTML.
    *   `css_properties_explanation.md`: File Markdown giải thích các thuộc tính CSS.
    *   `thuyet_trinh_du_an.md`: File tài liệu thuyết trình này.
*   **`animals/`:** Chứa các trang HTML chi tiết cho từng loài động vật (ví dụ: `dolphin.html`, `eagle.html`, `elephant.html`, `kangaroo.html`, `lion.html`, `panda.html`, `penguin.html`, `tiger.html`). Mỗi file này cung cấp thông tin, hình ảnh và âm thanh/video riêng của từng loài.
*   **`audio/`:** Chứa các file âm thanh và video được sử dụng trên trang web (ví dụ: `an-eagle-squawking-overhead-226774.mp3`, `dolphin-noise-6968.mp3`, `kang.mp4`, `panda.mp4`, `pen.mp4`, v.v.).
*   **`pic/`:** Chứa tất cả các file hình ảnh của động vật và các hình ảnh khác được sử dụng trên trang web (ví dụ: `dol.png`, `eal.png`, `ele.png`, `kang.png`, `lion.png`, `panda.png`, `pen.png`, `tiger.png`).
*   **`video/`:** Chứa các file video lớn hơn, ví dụ: `khidaucho.mp4`.

## 2. Cấu trúc HTML và các thẻ/thuộc tính quan trọng

Trang web sử dụng chuẩn HTML5 để cấu trúc nội dung.

### a. Bố cục chung (ví dụ `index.html`)

File `index.html` (trang chủ) thường tuân theo một bố cục phổ biến:

*   **`<head>`:** Chứa các thông tin meta (không hiển thị trực tiếp trên trang nhưng quan trọng cho trình duyệt và SEO), tiêu đề trang (`<title>`) và liên kết đến các tài nguyên bên ngoài.
    *   `<meta charset="UTF-8">`: Chỉ định bộ mã ký tự UTF-8 để hiển thị tiếng Việt và các ký tự đặc biệt khác một cách chính xác.
    *   `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Rất quan trọng cho **thiết kế đáp ứng (responsive design)**, đảm bảo trang web hiển thị và điều chỉnh phù hợp trên mọi thiết bị (máy tính, máy tính bảng, điện thoại).
    *   `<title>`: Tiêu đề sẽ hiển thị trên tab của trình duyệt.
    *   `<link rel="stylesheet" href="style.css">`: Liên kết đến file CSS chính để tạo kiểu cho trang.
*   **`<body>`:** Chứa tất cả nội dung hiển thị của trang web.
    *   **`<header>`:** Phần đầu trang, thường chứa tiêu đề trang, thanh điều hướng và có thể là một hình ảnh banner.
        *   `<img class="header-banner" src="path/to/banner.png" alt="Banner trang web">`: Hình ảnh banner. Thuộc tính `alt` cung cấp văn bản thay thế cho người dùng khi hình ảnh không tải được hoặc cho trình đọc màn hình hỗ trợ người khuyết tật.
        *   `<h1>` (hoặc tương tự): Tiêu đề chính của trang web.
        *   `<nav>`: Chứa các liên kết điều hướng (thường là các thẻ `<a>` trong `<ul>`/`<li>`).
            *   `<ul>`, `<li>`: Danh sách không có thứ tự để liệt kê các mục điều hướng.
            *   `<a href="page.html">`: Liên kết đến các trang khác.
    *   **`<main>`:** Chứa nội dung chính, duy nhất của trang đó.
        *   Có thể có phần "bài viết nổi bật" với video.
            *   `<video controls src="video/khidaucho.mp4">`: Nhúng một video. Thuộc tính `controls` sẽ hiển thị các điều khiển mặc định của video (phát/dừng, âm lượng, thanh tiến trình). Thuộc tính `src` chỉ định đường dẫn đến file video.
        *   Phần "lưới động vật" (`<div>` với `class="animal-grid"`) hiển thị nhiều loài động vật khác nhau.
            *   Mỗi động vật trong lưới thường là một `<div>` hoặc `<a>` với `class="animal-card"`.
            *   Bên trong một `animal-card` có:
                *   `<img src="path/to/pic.png" alt="Tên động vật" class="animal-image">`: Hiển thị hình ảnh động vật. `alt` rất quan trọng cho khả năng tiếp cận.
                *   `<h3>` (hoặc tương tự): Tên của động vật.
                *   `<p>`: Một đoạn mô tả ngắn.
    *   **`<footer>`:** Phần cuối trang, thường chứa thông tin bản quyền, liên hệ, v.v.

### b. Các trang chi tiết động vật (`animals/*.html`)

Các trang này (ví dụ: `animals/dolphin.html`, `animals/eagle.html`) có cấu trúc nhất quán:

*   Phần `<head>` tương tự như `index.html`.
*   Phần `<body>` thường sử dụng một thẻ `<table>` với `class="content-table"` để bố cục nội dung, chia thành một ô chứa hình ảnh và một ô chứa văn bản.
    *   `<h1>`: Tên của loài động vật.
    *   `<td>` với `class="image-cell"`: Chứa hình ảnh của động vật.
        *   `<img src="../pic/dol.png" alt="Cá heo" class="animal-image">`: Hiển thị hình ảnh. Lưu ý `../` được dùng để điều hướng đường dẫn tương đối (thoát ra một cấp thư mục, sau đó vào thư mục `pic/`).
    *   `<td>` với `class="text-cell"`: Chứa các mô tả bằng văn bản.
        *   `<h2>Mô tả chung</h2>`: Tiêu đề cho phần mô tả chung.
        *   **`<audio controls>` (Tôi đã thêm vào):** Đây là nơi trình phát âm thanh được thêm vào.
            *   `<source src="../audio/dolphin-noise-6968.mp3" type="audio/mpeg">`: Chỉ định file âm thanh. Thuộc tính `type` thông báo cho trình duyệt định dạng của âm thanh (`audio/mpeg` cho MP3, `video/mp4` cho MP4), giúp trình duyệt chọn codec phù hợp.
            *   `Trình duyệt của bạn không hỗ trợ phần tử âm thanh.`: Đây là văn bản dự phòng, chỉ hiển thị nếu trình duyệt của người dùng không hỗ trợ thẻ `<audio>`.
        *   `<p>`: Các đoạn văn bản mô tả.
        *   `<h2>Giao tiếp và Trí thông minh</h2>`: Tiêu đề khác.
    *   `<a href="https://en.wikipedia.org/wiki/Dolphin" target="_blank">`: Liên kết ngoài đến trang Wikipedia. `target="_blank"` mở liên kết trong một tab mới.
    *   `<a href="../index.html" class="back-button">`: Nút quay lại trang chủ.

### c. Các thẻ HTML và thuộc tính thường dùng:

*   **Cấu trúc:** `<html>`, `<head>`, `<body>`, `<header>`, `<main>`, `<footer>`, `<div>` (khối chung), `<span>` (phần tử nội dòng chung).
*   **Văn bản & Tiêu đề:** `<h1>` đến `<h6>` (các cấp tiêu đề), `<p>` (đoạn văn), `<a>` (liên kết), `<strong>` (in đậm), `<em>` (in nghiêng).
*   **Danh sách:** `<ul>` (danh sách không thứ tự), `<li>` (mục danh sách).
*   **Đa phương tiện:** `<img>` (hình ảnh), `<video>`, `<audio>`, `<source>`.
*   **Bảng:** `<table>`, `<tr>` (hàng trong bảng), `<td>` (ô dữ liệu trong bảng).
*   **Các thuộc tính quan trọng:**
    *   `src`: Chỉ định nguồn (URL) cho các phần tử đa phương tiện (`<img>`, `<video>`, `<audio>`).
    *   `href`: Chỉ định đích (URL) cho các siêu liên kết (`<a>`).
    *   `alt`: Cung cấp văn bản thay thế cho hình ảnh, rất quan trọng cho khả năng tiếp cận và khi hình ảnh không tải được.
    *   `class`: Gán một hoặc nhiều tên lớp cho một phần tử, được sử dụng rộng rãi để tạo kiểu bằng CSS.
    *   `controls`: Hiển thị các điều khiển phát lại mặc định (phát/dừng, âm lượng, v.v.) cho các phần tử `<video>` và `<audio>`.
    *   `type`: Chỉ định loại MIME của tài nguyên đa phương tiện (`<source>`), giúp trình duyệt xác định xem nó có thể phát file hay không.
    *   `target="_blank"`: Mở tài liệu được liên kết trong một cửa sổ hoặc tab mới.
    *   `lang="vi"`: Chỉ định ngôn ngữ chính của nội dung tài liệu là tiếng Việt.

## 3. Cách thức tạo kiểu bằng CSS (`style.css`) và các kỹ thuật

File `style.css` là xương sống cho giao diện và trải nghiệm người dùng của trang web. Nó sử dụng các thuộc tính và kỹ thuật CSS chuẩn để kiểm soát bố cục, màu sắc, phông chữ và khả năng thích ứng trên các kích thước màn hình khác nhau.

### a. Tạo kiểu chung và Kiểu chữ:
*   `body`: Đặt phông chữ toàn cầu (`font-family`), màu nền (`background-color`), màu chữ (`color`) và chiều cao dòng (`line-height`) để dễ đọc. `margin: 0` loại bỏ lề mặc định của trình duyệt.
*   `a`: Loại bỏ gạch chân liên kết (`text-decoration: none`) và kế thừa màu chữ.
*   `main`: Định nghĩa chiều rộng và chiều rộng tối đa của vùng nội dung chính, căn giữa theo chiều ngang (`margin: 20px auto`).

### b. Tạo kiểu Header (Đầu trang):
*   `.site-header`: Tạo kiểu cho nền header, đường viền, phần đệm (padding) và căn giữa nội dung.
*   `.header-banner`: Kiểm soát kích thước hình ảnh banner và đảm bảo nó phủ kín khu vực mà không bị méo (`object-fit: cover`).
*   `.site-title`: Đặt kích thước và độ đậm của phông chữ lớn cho tiêu đề chính.
*   `.main-nav-list`: Sử dụng `display: flex` và `justify-content: center` để tạo thanh điều hướng ngang, căn giữa và có khoảng cách đều giữa các mục (`gap`).
*   `.main-nav-list a`: Tạo kiểu cho các liên kết điều hướng (độ đậm phông chữ, màu sắc, padding). Thuộc tính giả (`:hover`) dùng để thay đổi màu liên kết khi di chuột vào.

### c. Tạo kiểu phần Bài viết/Video nổi bật:
*   `.featured-article`: Căn giữa nội dung trong phần này.
*   `.featured-header .featured-title`, `.sapo`: Tạo kiểu cho tiêu đề và phụ đề của nội dung nổi bật.
*   `.featured-video`: Đảm bảo phần tử video thích ứng (`width: 100%`, `max-width`) và được căn giữa.

### d. Bố cục lưới Động vật:
*   `.animal-grid`: Đây là phần quan trọng cho bố cục, sử dụng **CSS Grid** để tạo ra một bố cục linh hoạt và đáp ứng:
    *   `display: grid`: Kích hoạt bố cục lưới.
    *   `grid-template-columns: repeat(auto-fill, minmax(280px, 1fr))`: Một kỹ thuật mạnh mẽ cho thiết kế đáp ứng. Nó tạo ra nhiều cột nhất có thể vừa với màn hình, mỗi cột rộng ít nhất `280px` nhưng sẽ mở rộng để lấp đầy không gian có sẵn (`1fr`).
    *   `gap: 20px`: Thêm khoảng cách giữa các mục lưới.
*   `.animal-card`: Tạo kiểu cho từng thẻ động vật trong lưới (nền, đường viền, bo góc, tràn nội dung).
    *   `:hover`: Thêm hiệu ứng hình ảnh tinh tế (nâng lên và đổ bóng) khi di chuột qua thẻ (`transform: translateY(-5px)`, `box-shadow`).
*   `.animal-card img`: Đảm bảo hình ảnh trong thẻ thích ứng (`width: 100%`), duy trì tỷ lệ khung hình vuông (`aspect-ratio: 1 / 1`) và che phủ toàn bộ vùng chứa của nó (`object-fit: cover`).
*   `.animal-card .animal-name`, `.animal-desc`, `.details-text`: Tạo kiểu cho nội dung văn bản trong mỗi thẻ (kích thước phông chữ, độ đậm, màu sắc, lề, căn chỉnh văn bản).

### e. Tạo kiểu Footer (Cuối trang):
*   `.site-footer-main`: Tạo kiểu cho nền, màu chữ, căn chỉnh, padding và margin của footer.

### f. Liên kết danh mục Động vật:
*   `.animal-categories-links`: Căn giữa các liên kết danh mục.
*   `.category-links`: Sử dụng `display: flex` và `justify-content: center` để sắp xếp các nút danh mục theo chiều ngang với khoảng cách.
*   `.category-link-btn`: Tạo kiểu cho các nút danh mục (phông chữ, màu sắc, nền, padding, bo góc). Nó cũng loại bỏ gạch chân (`text-decoration: none`) và biến chúng thành `inline-block` để cho phép áp dụng padding. `:hover` thay đổi màu nền.

### g. Thiết kế đáp ứng (Responsive Design) với `@media`:
Một kỹ thuật quan trọng là sử dụng các **media queries (`@media`)** để điều chỉnh bố cục và kiểu dáng dựa trên kích thước màn hình thiết bị. Ví dụ, trong các trang chi tiết động vật (`animals/*.html`), có một media query như sau:

```css
@media (max-width: 768px) {
    .content-table {
        padding: 20px;
        border-spacing: 0;
    }
    .content-table tr, .image-cell, .text-cell {
        display: block;
        width: 100%;
    }
    .image-cell {
        margin-bottom: 20px;
    }
    h1 {
        font-size: 24px;
    }
}
```

Quy tắc này sẽ thay đổi bố cục cho các màn hình có chiều rộng tối đa `768px` (thường là máy tính bảng và điện thoại):
*   Nó điều chỉnh `content-table` để loại bỏ khoảng cách và thay đổi padding.
*   Quan trọng nhất, `display: block` được áp dụng cho các hàng bảng (`<tr>`), ô hình ảnh (`.image-cell`) và ô văn bản (`.text-cell`). Điều này khiến chúng xếp chồng lên nhau theo chiều dọc thay vì cạnh nhau, giúp bố cục bảng thích ứng tốt hơn trên màn hình nhỏ.
*   Các ô hình ảnh chiếm toàn bộ chiều rộng (`width: 100%`) và có thêm lề, kích thước phông chữ `h1` cũng được điều chỉnh.

Kỹ thuật `@media` này thể hiện cách tiếp cận **"thiết kế ưu tiên di động" (mobile-first)** hoặc **"thiết kế đáp ứng"**, đảm bảo trang web thân thiện và hấp dẫn trên mọi loại thiết bị.

## 4. Tích hợp âm thanh/video (Những thay đổi tôi đã thực hiện)

Đóng góp chính của tôi là thêm trình phát âm thanh tương tác vào các trang chi tiết động vật.

*   **Kỹ thuật được sử dụng:** Nhúng phần tử `<audio>` chuẩn HTML5.
*   **Ví dụ mã (từ `animals/dolphin.html`):**
    ```html
                    <h2>Mô tả chung</h2>
                    <audio controls>
                        <source src="../audio/dolphin-noise-6968.mp3" type="audio/mpeg">
                        Trình duyệt của bạn không hỗ trợ phần tử âm thanh.
                    </audio>
                    <p>
                        Cá heo là loài động vật có vú sống ở biển...
                    </p>
    ```
*   **Giải thích:**
    *   **`<audio>`:** Thẻ HTML5 này dùng để nhúng nội dung âm thanh.
    *   **`controls`:** Thuộc tính này rất quan trọng. Nó hiển thị các điều khiển âm thanh mặc định (nút phát/dừng, thanh trượt âm lượng, thanh tiến trình) cho người dùng, làm cho âm thanh có thể tương tác. Nếu không có `controls`, âm thanh sẽ phát nền mà không có cách nào để người dùng điều khiển.
    *   **`<source src="../audio/dolphin-noise-6968.mp3" type="audio/mpeg">`:** Thẻ `<source>` chỉ định tài nguyên đa phương tiện.
        *   **`src`:** Trỏ đến file âm thanh (`../audio/dolphin-noise-6968.mp3`). `../` có nghĩa là "đi lên một cấp thư mục từ thư mục hiện tại (`animals/`), sau đó vào thư mục `audio/`".
        *   **`type="audio/mpeg"`:** Thuộc tính này cho trình duyệt biết loại MIME của file âm thanh. Đối với file `.mp3`, đó là `audio/mpeg`. Đối với file `.mp4` (có thể chứa cả âm thanh hoặc video), đó sẽ là `video/mp4`. Điều này giúp trình duyệt nhanh chóng xác định xem nó có thể phát file hay không mà không cần tải toàn bộ file.
    *   **`Trình duyệt của bạn không hỗ trợ phần tử âm thanh.`:** Văn bản này chỉ hiển thị nếu trình duyệt của người dùng không hỗ trợ thẻ `<audio>` của HTML5, cung cấp một thông báo dự phòng thân thiện.

## 5. Các quan sát và kỹ thuật khác

*   **Cách đặt tên file:** Các file được đặt tên một cách nhất quán (ví dụ: `dolphin.html`, `eagle.html`), giúp dễ quản lý.
*   **Đường dẫn tương đối:** Dự án sử dụng rộng rãi các đường dẫn tương đối (`../pic/dol.png`, `../index.html`, `../audio/...`), giúp trang web dễ dàng di chuyển trong cấu trúc thư mục của nó.
*   **Khả năng tiếp cận (thuộc tính `alt`):** Hình ảnh luôn sử dụng thuộc tính `alt`, đây là một thực hành tốt cho khả năng tiếp cận (dành cho người dùng sử dụng trình đọc màn hình) và tối ưu hóa công cụ tìm kiếm (SEO).
*   **Ngôn ngữ (`lang="vi"`):** Thẻ `<html>` sử dụng `lang="vi"` để chỉ ra rằng nội dung chính của tài liệu là tiếng Việt.

Bản tóm tắt toàn diện này sẽ cung cấp cho bạn tất cả thông tin cần thiết để chuẩn bị bài thuyết trình, bao gồm "cái gì", "làm thế nào" và "tại sao" của mã và các kỹ thuật được sử dụng trong dự án này. Nếu bạn cần tôi giải thích thêm bất kỳ phần cụ thể nào, hãy cho tôi biết!
