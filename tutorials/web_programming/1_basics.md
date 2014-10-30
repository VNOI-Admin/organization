# Cơ bản về code web

## Điều gì xảy ra khi bạn gõ URL vào browser?

Khi bạn gõ URL vào browser, rồi Enter:

1. Browser gửi một HTTP request đến web server. Một HTTP request thông thường gồm:
    - URL
    - Thông tin về browser (cái này khá cần thiết, ví dụ để nhận dạng bạn đang truy cập vào bằng máy tính hay điện thoại).
    - Dữ liệu bạn gửi lên (ví dụ khi login, browser cần gửi lên username và password).
2. Server nhận được HTTP request, xử lý và trả lại một HTTP response. Một HTTP response thông thường gồm:
    - HTTP response code: cho biết truy cập thành công hay không. Ví dụ:
        - 200 --> thành công
        - 404 --> bạn không có quyền truy cập link
    - HTML: những thứ được hiển thị trên browser.

Trên server:
- Dữ liệu của bạn được lưu vào database để có thể query nhanh. Database thông thường được cài bằng các cây cân bằng và hash.
- Trên server, một ngôn ngữ lập trình được sử dụng để query dữ liệu từ database, xử lý dữ liệu và tạo ra HTTP response.

## Database

Ở server, database được dùng để lưu trữ dữ liệu. Để hiểu tại sao cần dùng database & hướng dẫn sơ qua về database, đọc ở [đây](./2_database.md)
