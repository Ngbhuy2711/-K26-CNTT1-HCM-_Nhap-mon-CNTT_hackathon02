# BÀI LÀM – HACKATHON 02

- **Mã đề:** 01
- **Họ tên:** Nguyễn Bảo Huy
- **Lớp:** 
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
ls -Force
mkdir backup
cp .\data\Ban_Ve_Thang_1.xlsx.xlsx .\backup
rm *.tmp

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-r---        11/11/2026   7:52 AM                data
d-r---        11/11/2026   7:50 AM                docs
d-r---        11/11/2026   7:50 AM                evidence
d-r---        11/11/2026   7:52 AM                logs
d-r---        11/11/2026   7:48 AM                web
-a----         11/3/2026   7:06 AM             74 .env
-a----         11/3/2026   7:06 AM           2407 bai_lam.md
-a----         11/3/2026   7:06 AM            158 Ghi_Chu_Ban_Giao.txt.txt
-a----         11/3/2026   7:06 AM             22 temp_101.tmp


```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
Select-String "status=500" .\logs\visit > .\logs\loi_500.txt

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-01-28 08:24:34 POST /api/thanh-toan status=500
2026-01-28 08:28:45 POST /api/thanh-toan status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
(Get-Content .\logs\visit.log | Select-String "Status=404").count

```

```text
4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Ghi lệnh vào đây (xoá dòng này)

```

### Nội dung file logs/tong_hop.txt

```text
(Dán nội dung file vào đây – xoá dòng này)

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** 
- **Expected:** 
- **Actual:** 
- **Log:** 

### Câu tìm kiếm Google

```text
(Ghi câu tìm kiếm vào đây – xoá dòng này)

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/ban_ve_thang_1.xlsx`, không cần ghi vào đây.
