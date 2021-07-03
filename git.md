## Thiết lập chứng thực cá nhân
```
$ git config --global user.name "User Name"  
$ git config --global user.email "username@gmail.com"
```

## Tạo một kho chứa Git
```
$ git init
```

## Sao chép một kho chứa đã tồn tại
```
$ git clone https://github.com/user/repository.git
```
Câu lệnh trên sẽ tạo một thư mục mới có tên giống trên của Repo.

## Nhánh trong git
Khi sử dụng Git, bạn có thể tạo ra nhiều nhánh (branch) khác nhau. Câu lệnh Git này dùng để kiểm tra branch hiện tại:
```
$ git branch
```

Để tạo mới một branch:
```
$ git branch <name_branch>
```

Để chuyển và tạo mới:
```
$ git branch -b <name_branch>
```

## Chuyển nhánh(branch)
```
$ git checkout <name_branch>
```

## Cập nhật thay đổi
Sau khi bạn thay đổi source code: thêm mới, sửa, xoá files,… Bạn cần phải cập nhật lên Staging Area. Để cập nhật hết các files:
- Để add tất cả các file
```
$ git add .
```
- Để add file hoặc folder cụ thể 
```
$ git add <Tên file hoặc folder>
```
Sau lệnh add, bạn cần sử dụng câu lệnh Commit để đây thông tin thay đổi lên Local Respository:
```
$ git commit -m "Message"
```
## Cập nhật lên server
Sau câu lệnh Commit, thông tin mới chỉ được cập nhật lên Local Repository. Nếu muốn cập nhật lên server thì bạn phải sử dụng câu lệnh push:
```
$ git push origin <name_branch>
```

## Gộp nhánh
Sau một thời gian cập nhật các file và push lên git trên branch mới, bây giờ mình cần ghép (merge) code lại vào nhánh gốc (master). Trước tiên, cần phải checkout ra khỏi branch hiện tại cần gộp để vào branch master, sau đó thì dùng lệnh merge để ghép branch mới vào master:
```
$ git checkout master
$ git merge <new_branch>
```

## Xem lại lịch sử commit
```
$ git log
```

## Xem thay đổi trước khi push
```
$ git diff
```

## Gộp commit
```
$ git rebase -i HEAD~
```
Sau dấu ~ là số commit bạn muốn gộp. Sau khi gõ lệnh này một cửa sổ trình soạn thảo hiện ra. Thay đổi ký tự pick của dòng các dòng sau dòng đầu thành s rồi lưu lại/kết thúc. Khi đó, trình soạn thảo để chỉnh sửa giải thích commit thiết lập cho commit sau khi đã tổng hợp sẽ được hiển thị, nên hãy chỉnh sửa lưu lại/kết thúc.

## Pull từ remote repository
```
$ git pull 
```
Lệnh trên sẽ gộp những thay đổi mới kéo về từ máy chủ từ xa với nhánh hiện tại trên máy local.

