# "Nghịch" Git

## Git project trông như thế nào?

Trong phần hướng dẫn này, mình sẽ lấy ví dụ bằng Project VNOI-Admin/organization. Khi click vào [link](https://github.com/VNOI-Admin/organization), những gì bạn đang nhìn thấy chính là một Git Project, được lưu trên Github. Github là một server để lưu trữ Git Project (chú ý rằng, vì Git là Distributed Version Control, nên khi bạn lôi Project từ Github về máy tính cá nhân, thì Project trên máy bạn và Project trên Github có vai trò tương đương nhau, và máy của bạn cũng có thể được dùng làm server để các máy khác copy Project này về).

Để lôi Git Project từ Github về máy của bạn:

1. [Setup Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
Với windows, cần cài them Git bash. Với Linux / MacOS chỉ cần dùng terminal là ok.

2. Clone project từ Github về:

```
git clone https://github.com/VNOI-Admin/organization.git
```

Sau khi clone về, bạn sẽ thấy 1 folder có cấu trúc giống hệt với Git Project trên Github.

## Làm việc với Git

### Pull
Giờ giả sử bạn muốn code thêm vào Git Project (ví dụ, bạn có thể thêm thông tin cá nhân của mình vào file admin.md).

Đầu tiên, bạn cần đảm bảo Git Project của mình "up-to-date", nghĩa là có tất cả những thay đổi mới nhất ở trên Server, bằng cách:

```
git pull origin master
```

Trong câu lệnh trên:
* origin là "nguồn" của Project, trong trường hợp này là Github, vì bạn clone project từ Github.
* master là một _branch_ của Project. Một Project có thể có rất nhiều branch. Ví dụ: X và Y cùng làm 1 game. X viết phần logic, Y viết phần giao diện. Để làm việc độc lập, 2 người có thể làm việc trên 2 branch khác nhau, rồi về sau _merge_ 2 branch lại

### Add & Commit

Bước tiếp theo là thực hiện những thay đổi mà bạn muốn. File admin.md được viết theo Markdown syntax để có thể hiển thị trực tiếp trên Github. Syntax Markdown khá đơn giản nên bạn có thể đoán được. Những syntax thường dùng có thể tìm thấy ở [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

Sau khi thay đổi, bạn cần tạo ra 1 version mới của Project. Làm việc này bằng cách:

```
git add admin.md
git commit -m "Một dòng ngắn gọn mô tả những gì bạn đã thay đổi"
```

git add admin.md đánh dấu lại là bạn muốn thêm những thay đổi của file admin.md vào version đc tạo ra tiếp theo
git commit tạo ra một version mới của Project.

Chú ý rằng lúc này, version được tạo ra chỉ nằm trên máy tính cá nhân của bạn.

### Push

Để lưu version bạn vừa tạo ra lên Github, bạn cần push version vừa tạo ra lên Github:

```
git push origin master
```

Trong câu lệnh trên, ý nghĩa của origin và master giống như đã giải thích ở phần Pull

## Bài tập
* Tự clone project, pull, commit & push
