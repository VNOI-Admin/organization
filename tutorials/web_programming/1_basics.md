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

### Tại sao dùng database

Như ở trên đã nói, dữ liệu của user được lưu trong database. Để hiểu tại sao chúng ta lại cần lưu vào database mà không đơn giản lưu vào file, cần phải hiểu những điểm khác biệt cơ bản giữa database và file:

* Database cho phép insert, delete, update data hiệu quả. Ví dụ giả sử bạn có 1 file dữ liệu chứa thông tin của $10^6$ người dùng, mỗi người dùng có username, tên, tuổi, password, ngày sinh... Cách đơn giản nhất là lưu tất cả thông tin này vào 1 file $10^6$ dòng. Nhưng như vậy rất khó update, do bạn không thể thay đổi 1 dòng ở giữa file, dẫn đến mỗi lần thay đổi thông tin user, bạn phải ghi lại tối đa $10^6$ dòng.
* Database cho phép nhiều người cùng lấy thông tin từ database.
* Dựa vào kinh nghiệm, người ta nhận thấy rằng, đa số các thao tác làm việc với dữ liệu đều chỉ có 1 số loại nhất định. Lấy ví dụ với Facebook:
    - User sửa hình đại diện --> Update thông tin của 1 user
    - User like ảnh --> Insert thêm 1 thông tin mới về like
    - Một user mới đăng ký --> Insert thêm 1 thông tin mới về user
    - User post status --> Insert 1 thông tin mới về post
    Do các thao tác với dữ liệu thường lặp đi lặp lại, người ta đã tạo ra những ngôn ngữ bậc cao hơn (SQL) dùng cho database, để query và update dữ liệu.

### Database trông như thế nào

Các database truyền thống thường được thiết kế theo dạng bảng, với nhiều cột chứa attribute của dữ liệu, mỗi dòng là 1 record, 1 dữ liệu mới.

Ví dụ:

Ở đây mình có 1 database VOJ do mình tự tạo. Database này gồm nhiều bảng. Mình có thể liệt kê các bảng này bằng lệnh SQL:

```sql
show tables;
```

<img src="./../../assets/img/database/table_list.png" alt="show tables" width="566px" height="251px" />

