# Báo cáo Bài 4: Quản lý .gitignore và Sửa lịch sử (Amend)

## 1. Mục tiêu
Gỡ file nhạy cảm credentials.txt khỏi sự theo dõi của Git (nhưng vẫn giữ file trên máy), cấu hình .gitignore để bỏ qua file này về sau, và sửa thông điệp commit gần nhất bằng --amend.

## 2. Gỡ file khỏi cache theo dõi của Git

Lệnh sử dụng:
git rm --cached credentials.txt

Giải thích:
- Tùy chọn --cached chỉ gỡ file ra khỏi vùng theo dõi (staging/index) của Git.
- File credentials.txt VẪN được giữ nguyên trong thư mục làm việc, không bị xóa vật lý khỏi ổ đĩa.
- Nếu chỉ dùng "git rm credentials.txt" (không có --cached) thì file sẽ bị xóa cả trên đĩa — điều này cần tránh.

## 3. Cấu hình .gitignore

Tạo file .gitignore với nội dung:
credentials.txt
.env
.DS_Store
node_modules/

Mục đích: Git sẽ tự động bỏ qua các file/thư mục này, không theo dõi và không commit chúng trong tương lai.

## 4. Sửa thông điệp commit gần nhất bằng --amend

Lệnh sử dụng:
git commit --amend -m "Remove credentials.txt from tracking and add .gitignore"

Giải thích:
- --amend sửa lại commit gần nhất (thay đổi message hoặc nội dung) mà không tạo thêm commit mới.

## 5. Kiểm tra kết quả

Kiểm tra trạng thái:
git status
=> credentials.txt không còn xuất hiện