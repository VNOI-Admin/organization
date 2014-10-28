# Những lệnh làm việc với git

Trong phần này, mình giới thiệu khá nhiều lệnh làm việc với git. Các bạn nên đọc qua 1 lần cho biết mình có thể làm những gì với git, rồi về sau lúc cần làm gì thì có thể tìm lại trong này.

## Help

Để xem giải thích chi tiết về 1 lệnh, ví dụ git add:

```
git help add
```

## Remove file

Ngược lại với git add là git remove: Khi bạn muốn xóa 1 file khỏi Git Project (có thể do trước đó add & commit nhầm):

```
git rm /path/to/file
```

Chú ý:
* Nếu bạn muốn mới add và chưa commit file, khi git rm sẽ bị lỗi:
```
error: the following file has changes staged in the index
```

Nếu bạn muốn vừa xóa file khỏi Git Project, vừa xóa hoàn toàn file đó, cần thêm option -f:

```
git rm -f /path/to/file
```

Nếu bạn chỉ muốn xóa file khỏi Git Project (nghĩa là Git không track file đó nữa, nhưng file đó vẫn tồn tại), thêm option --cached

```
git rm --cached /path/to/file
```

## Diff

Để xem chi tiết bạn đã thay đổi những gì, dùng git diff:

```
git diff
```

Chú ý: mặc định, git diff so sánh những file đang trong trạng thái modified với file ở version cuối. Như vậy, nếu bạn đã git add, thì những thay đổi sẽ không được nhìn thấy. Để so sánh trạng thái của staged files với file ở version cuối, dùng:

```
git diff --cached
```

## Move

Để di chuyển 1 file, dùng:

```
git mv /old/path /new/path
```

Thực ra, git đủ thông minh để nếu bạn đổi tên file không qua git, và git rm file đã bị xóa + git add file mới, thì Git sẽ tự phát hiện ra file đó đã được đổi tên.

## Add

Để add tất cả các file đã được thay đổi:

```
git add --all
```

_CHÚ Ý_ rằng lệnh này cần hạn chế dùng, để tránh commit nhầm những thứ bạn không muốn. Khi git add --all, bạn cần biết rất rõ mình đang làm gì.

Một nguyên tắc quan trọng khi làm việc với git là bạn cần phải commit thường xuyên, và cực kỳ hạn chế những lần commit có đến hàng chục file bị thay đổi. Mỗi lần bạn muốn thay đổi gì, thay đổi vài file một, và commit với 1 commit message dễ hiểu để về sau có thể tìm lại.

Để tránh commit nhầm file, bạn có thể thêm những file bạn không bao giờ muốn commit vào file .gitignore. Ví dụ, bạn có thể tìm thấy file .gitignore trong folder của project VNOI này chứa:

* *.swp --> không bao giờ add những file đuôi .swp (file này là file được sinh ra bởi Vim)

[Đọc thêm về gitignore](http://git-scm.com/docs/gitignore)

# Undo

Nếu bạn vừa commit và phát hiện ra commit nhầm, bạn có thể sửa commit lại bằng cách:

```
git add /file/cần/commit/hoặc/file/được/sửa/thêm
git commit --amend
```

_CHÚ Ý_ rằng bạn chỉ được dùng git commit --amend nếu bạn chưa push. Lý do là git commit --amend làm thay đổi lịch sử của Git Project, nên nếu bạn đã push, rồi lại git commit --amend, sau đấy push, thì lịch sử trên Github sẽ bị loạn. Sẽ vô cùng tệ nếu đã có người pull commit của bạn về. Lúc này máy của bạn và máy người đã pull sẽ có lịch sử khác nhau và rất khó để merge.

Nếu bạn add nhầm 1 file vào stage (và chưa commit), và muốn undo:

```
git reset HEAD /path/to/file
```

Nếu bạn sửa nhầm 1 file và muốn cho nó về lại giống như version cuối:

```
git checkout -- /path/to/file
```

# Git merge

Giả sử có 2 người A, B và 1 server S. Ban đầu A và B clone project từ S.
* A pull
* B pull
* A thay đổi 1 số file
* A commit & push
* B thay đổi 1 số file
* B commit & push

Lúc này, B sẽ không thể push được do B đang không có bản mới nhất của Project. (chú ý rằng B có thể push được nếu dùng git push -f, nhưng làm vậy sẽ làm mất commit của A. Do đó bạn không được dùng git push -f trừ khi biết rõ mình đang làm gì).

Để có thể push được, B có thể
```
git pull origin master
```

Bản chất của lệnh pull là gồm 2 lệnh:

```
git fetch origin master
git merge origin/master
```

git fetch origin master lấy những thay đổi ở trên server về
git merge origin/master merge trạng thái hiện tại của Project với origin/master: bản mới nhất ở server. Để merge, git sẽ cố gắng "làm tốt nhất có thể": nếu A và B thay đổi file ở các vùng khác nhau của file, cả thay đổi của A và B sẽ đc giữ trên file mới. Nếu A và B thay đổi cùng 1 dòng, git merge sẽ bị lỗi. Lúc này file bị cả 2 thay đổi sẽ ở trong tình trạng "unmerged", và nếu mở bằng text editor sẽ thấy nó trông thế này:

```
<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
  please contact us at ...
</div>
>>>>>>> iss53:index.html
```

Lúc này bạn cần tự sửa file này (có thể dùng tay hoặc git merge tools - google trên mạng), rồi

```
git add /file/đã/merge
```

Sau khi merge xong tất cả các file, bạn git

```
git commit
```

Để đánh dấu là đã merge xong và tạo 1 version mới.

## Bài tập:
* Nghịch thử các lệnh này
* Khi nghịch chán, reset lại project bằng cách clone lại từ đầu

