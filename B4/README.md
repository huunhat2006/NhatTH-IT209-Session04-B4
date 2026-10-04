# Báo cáo: Bài 4 - Quản lý tệp tin bỏ qua (.gitignore) và Sửa lịch sử (Amend)

## Cách gỡ bỏ file khỏi cache của Git
Để gỡ bỏ file `credentials.txt` vô tình bị commit khỏi sự theo dõi của Git (nhưng vẫn giữ lại file vật lý trên ổ cứng), ta sử dụng lệnh:
```bash
git rm --cached credentials.txt
```
Lệnh này xóa tệp khỏi Staging Area (index) của Git, khiến nó trở thành untracked file, nhưng không tác động đến nội dung thực tế trên thư mục làm việc (Working Directory).

Sau đó, tiến hành thêm file `credentials.txt` vào file `.gitignore` để tránh Git theo dõi lại tệp này trong tương lai.

## Chỉnh sửa thông điệp commit
Sau khi gỡ file khỏi cache và tạo `.gitignore`, để gộp chung thay đổi này và sửa lại thông điệp commit gần nhất đã bị sai, ta sử dụng lệnh `--amend`:
```bash
git add .gitignore
git commit --amend -m "Add project settings (credentials removed)"
```

## Kết quả hiển thị của lệnh `git log -n 1`
Dưới đây là kết quả kiểm tra lịch sử commit chứng minh đã sửa đổi thành công:
```
commit 77046449a57bd8ddf8f6c87d72302de6083246fe
Author: Huunhat123 <huunhat20052006@gmail.com>
Date:   Sun Oct 4 19:15:33 2026 +0700

    Add project settings (credentials removed)
```
