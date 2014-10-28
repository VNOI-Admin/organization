# Giới thiệu

## Version control là gì?

Version control là một chương trình giúp:

* Lưu lại tất cả các thay đổi với 1 hoặc nhiều file, để bạn có thể lấy lại 1 file ở một thời điểm trong quá khứ (gọi là 1 *version* cũ)

Để lưu lại các version cũ của 1 file, cách đơn giản nhất mà bạn có thể làm là: Mỗi ngày, copy tất cả các file của bạn vào 1 folder, đặt tên theo ngày đó. Để lấy lại 1 version cũ của 1 file, bạn chỉ cần tìm ngày tương ứng của nó. Tuy nhiên, cách này rất thiếu hiệu quả:

* Tốn bộ nhớ: Giả sử bạn làm việc với 1 project trong suốt 1 năm --> 365 lần copy toàn bộ project
* Dễ gây nhầm lẫn: nếu copy nhầm file làm thay đổi 1 bản cũ?

Để đáp ứng nhu cầu quản lý version của file, các "Version control" được tạo ra. Một trong những version control đầu tiên là rcs, hoạt động bằng cách lưu các thay đổi vào 1 database. Tuy nhiên cách làm này vẫn còn nhược điểm là nếu hỏng ổ cứng thì tất cả dữ liệu vẫn mất hết, và không hỗ trợ nhiều người cùng làm việc với 1 project.

Tiếp đó, subversion ra đời. Subversion là "Centralized version control": tất cả các dữ liệu (ở đây là tất cả các thay đổi lên các file) được lưu ở 1 server chung. Cách làm này cho phép nhiều người cùng làm việc với nhau, nhưng vẫn có nhược điểm là chậm (mỗi lần muốn lưu thay đổi lên file cần phải kết nối đến server), và ngoài ra nếu server sập thì tất cả không lưu dữ liệu đc, và nếu server hỏng ổ cứng thì tất cả dữ liệu mất hết.

Học được từ những nhược điểm của các Version control trước, Git ra đời. Git là một "Distributed Version Control", nghĩa là với git, có nhiều máy có vai trò tương đương nhau (mỗi máy đều có thể coi là 1 server). Mỗi máy đều có thể giữ toàn bộ thông tin cần có của cả Project. Một máy cũng có thể đc kết nối với nhiều server, mỗi server cho phép một nhóm người khác nhau cùng làm việc.

## Git là gì?

Git ra đời vào năm 2005, được viết bởi Linus Torvalds để dùng cho hệ điều hành Linux. Chính vì được dùng cho một hệ thống code cực lớn như Linux, nên Git được thiết kế với những đặc điểm quan trọng:

* Nhanh
* Đơn giản
* Hỗ trợ hàng nghìn nhánh (branch) cùng tồn tại (sẽ giải thích thêm sau)
* Distributed
* Có thể sử dụng cho những project rất lớn.

## Đọc thêm:

* [Wikipedia - Git software](http://en.wikipedia.org/wiki/Git_(software))

