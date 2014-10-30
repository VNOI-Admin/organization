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

## Server side Programming languages

Khi một HTTP request được gửi đến web server, nó sẽ được xử lý bởi những đoạn code được viết bằng 1 hoặc nhiều ngôn ngữ lập trình. Những đoạn code này có thể được viết bởi gần như bất kỳ ngôn ngữ nào (kể cả C++, Java), nhưng những năm gần đây phổ biến nhất là Python, PHP, Ruby, JavaScript và Go.

VNOI forum (vnoi.info) được viết bằng PHP, dùng Joomla framework (khái niệm Framework sẽ được giải thích sau). Hiện tại, VNOI được dự định code lại bằng Python, dùng Django framework.

## Client side Programming languages

Ở client side, có 3 "ngôn ngữ" được sử dụng: HTML, CSS và Javascript. (Đặt ngôn ngữ trong "" vì nhiều người ko tán thành việc gọi HTML và CSS là ngôn ngữ lập trình).

HTML là Hyper Text Markup Language. Nó giúp browser hiểu được bố cục của trang web. Bạn có thể dễ dàng xem code HTML của trang web bất kỳ bằng bấm chuột phải vào và view page source. Vì cũng là markup language, nên HTML và Markdown có nhiều điểm giống nhau: cũng có Header, list, link... Nhưng HTML có nhiều luật phức tạp hơn.

CSS là Cascade Style Sheet. Nó giúp browser biết cần phải hiển thị các element như thế nào. (màu sắc, kích thước chữ, khoảng cách giữa các thành phần của trang...)

JavaScript là ngôn ngữ được chạy ở browser. Nó cho phép trang web "có thể thay đổi được". Ví dụ, khi bạn nhìn thấy 1 cái gì đấy chuyển động trên trang web, một menu bar hiện ra, một popup box hiện lên... thì hầu hết đều là nhờ JavaScript.

Chỉ với HTML, CSS và JavaScript, bạn có thể tạo được 1 trang web tĩnh (không có dữ liệu, và hiển thị các thông tin giống hệt nhau với tất cả các user, user không thể login...).

## Thiết kế hiện tại của bảng rank VOJ.

[Bảng rank VOJ](https://ngthanhtrung23.github.io/VOJRanklist) gồm 2 components:

1. Python: Trên 1 webserver, mình đặt đoạn code Python làm các nhiệm vụ:
    - Lấy dữ liệu từ SPOJ về
    - Tính điểm từng user
    - Push dữ liệu lên rank VOJ trên Github.

2. Web component: Phần web chỉ gồm HTML, CSS và JavaScript. [Tất cả code được lưu trên Github](https://github.com/ngthanhtrung23/VOJRanklist). Phần code gồm HTML, CSS tĩnh và JavaScript (chạy trên browser) để thêm dữ liệu vào bảng rank. Nói cách khác, khi user load trang web về, chỉ có khung HTML và CSS rỗng. Sau đấy browser chạy JavaScript, JavaScript tạo ra thêm HTML của bảng rank và danh sách bài, rồi chèn vào HTML.
