#Description
###Mục tiêu
Project có mục tiêu xây dựng một platform đồng nhất cho các bạn  yêu thích tin học Việt Nam trao đổi, tìm kiếm thông tin ... giao lưu bla blaa..
###Người sử dụng

- Admin: Người quản lí trang web, có tài khoản cá nhân, có mọi quyền đối với user acc và database
- User: Người dùng, có tài khoản cá nhân và có một số quyền hạn nhất định
- Visitor: Người có thể access trang web, không có tài khoản cá nhân
- ** (Vì sau này có thể có thêm một số vai trò khác nữa)

###Assumptions and Constraints
(to be fulfill)

#Các chức năng chính
###1. Forum 
Forum là nơi ....

Các chức năng chính là:

1. Trao đổi thuật toán các bài
    1. User có thể create/edit thread
    2. Only Admin can delete thread
    2. User can comment a thread or a comment (tree-structure)
2. Tạo tài khoản, login và quản lí tài khoản cá nhân
    1. User can register a new account (acc is different from VOJ acc)
        1. User cần có unique username, password, email, VOJ acc?
        2. How to verify?
    2. User có thể thay đổi thông tin cá nhân (trừ username)
3. New feeds (much like codeforces)
    1. Admin có thể tạo và pin những post quan trọng lên homepage
    2. Home page display most recent posts 
    3. User có thể tạo post không?
4. Notification center
    1. Mỗi khi có người nhắc đến trong một post/thread/comment, user sẽ đc notify (like Facebook)
3. Message center
    1. User can send/receive message from other users
    2. Mailbox displays on homepage

###2. Thư viện tài liệu
  1. Cho phép User upload:
    1. Useful links
    2. Video
    3. Documents

###3. Voj interface
1. User có thể đọc đề  VOJ từ trang web
2. User can submit to VOJ Judge via trang web
    - Làm thế nào lưu pass voj hiệu quả?
    - Tạo account của vnoi để submit?
    - Mỗi account chỉ đc có 2 submission trong queue
    - Cần 100 accounts?
3. User can see Ranklist
4. Interface cho các oj khác
5. Dịch đề?

#Định nghĩa một số thuật ngữ đã dùng

#Judge (phase 2)

