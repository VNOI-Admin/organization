#Description
##Mục tiêu
Project có mục tiêu xây dựng một platform đồng nhất cho các bạn  yêu thích tin học Việt Nam trao đổi, tìm kiếm thông tin ... giao lưu bla blaa..
##Người sử dụng

- Admin: Người quản lí trang web, có tài khoản cá nhân, có mọi quyền đối với user acc và database
- User: Người dùng, có tài khoản cá nhân và có một số quyền hạn nhất định
- Visitor: Người có thể access trang web, không có tài khoản cá nhân
- ** (sau này có thể có thêm một số vai trò khác nữa)

##Assumptions and Constraints

- (to be fulfill)



#Các chức năng chính
##1. Forum 
Forum là nơi ....

Các chức năng chính là:

1. Trao đổi thuật toán các bài
    1. User có thể tạo (create) hoặc chỉnh sửa (update) thread
    2. Chỉ có admin mới xoá được thread 
    3. User có thể comment 1 thread hoặc comment vào 1 comment (tree-structure)
2. Tạo tài khoản, login và quản lí tài khoản cá nhân (hay VNOI acc)
    1. User can register a new account (acc is different from VOJ acc)
        1. User cần có unique username, password, email, VOJ acc?
        2. How to verify?
    2. User có thể thay đổi thông tin cá nhân (trừ username)
3. User có thể quản lí link từ VNOI account của mình tới VOJ account (Để có thể xem những bài mình đã làm, submit..)
    1. User có thể link VNOI acc tới một (và chỉ một) VOJ account 
	2. User có thể unlink VOJ acc
	3. Sau khi unlink, User có thể link tới một VOJ acc khác.
4. New feeds (much like codeforces)
    1. Admin có thể highlight/ bỏ highlight một số thread
    	1. Mỗi thread cần một button để highlight/un-highlight
    2. Home page cần hiện thị highlighted threads
    3. 4rum page cần hiện thị những thread gần đây nhất
5. Notification center
    1. Mỗi khi có người nhắc đến trong một thread/comment, User sẽ đc notify (like Facebook)
3. Message center
    1. User can send/receive message from other users
    
##2. Thư viện tài liệu
1. Cho phép User upload:
    1. Useful links
    2. Video
    3. Documents 

##3. Voj interface
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

