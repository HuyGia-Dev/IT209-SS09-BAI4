# Bài 4: Lưu trữ dữ liệu đơn giản với Docker Volume

Các lệnh đã thực hiện để tạo và kiểm tra Docker Volume:

1. **Tạo Named Volume mới tên là `easy-volume`:**
   ```bash
   docker volume create easy-volume
   ```

2. **Dùng container Alpine ghi nội dung vào volume:**
   ```bash
   docker run --rm -v easy-volume:/data alpine sh -c "echo 'Luu tru du lieu Docker' > /data/test.txt"
   ```

3. **Dùng container Alpine thứ hai đọc lại nội dung tệp để kiểm tra:**
   ```bash
   docker run --rm -v easy-volume:/data alpine cat /data/test.txt
   ```

**Kết quả mong đợi:**
Terminal in ra:
```text
Luu tru du lieu Docker
```