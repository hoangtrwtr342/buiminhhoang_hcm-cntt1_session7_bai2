Bài 2 : Phân tích Lỗi 404 từ File Log Máy chủ


Phần 1 — Phân tích

Get-ChildItem -Filter "*404*" tìm tên file hoặc thư mục có chứa 404 trong thư mục hiện tại; nó không đọc nội dung file để tìm dòng lỗi. Vì vậy, nếu 404 chỉ xuất hiện trong nội dung log chứ không nằm trong tên file, kết quả có thể trống.

Để tìm nội dung bên trong file, dùng Select-String.


Phần 2 — Sửa lỗi

Lệnh là : Get-ChildItem -Recurse -Filter access.log | Select-String -Pattern 'ERROR'
