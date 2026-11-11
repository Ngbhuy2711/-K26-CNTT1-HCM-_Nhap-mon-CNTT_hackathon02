# BÀI LÀM – HACKATHON 02

- **Mã đề:** 01
- **Họ tên:** Nguyễn Bảo Huy
- **Lớp:** CNTT1
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
ls -Force
mkdir backup
cp .\data\Ban_Ve_Thang_1.xlsx.xlsx .\backup
rm *.tmp
pwd
cd 

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
@'
>> # Script : tong_hop.ps1
>> # Tac gia :  NGUYEN BAO HUY
>> # Ngay tao : 11-11-2026
>> Write-Host "Dang tao bao cao..."
>> "=== BAO CAO SU CO WEBSITE ===" > logs/tong_hop.txt
>> Get-Content logs/visit.log | Select-String "status=404" >> logs/tong_hop.txt
>> Get-Content logs/visit.log | Select-String "status=500" | Measure-Object >> logs/tong_hop.txt
>> Write-Host "Hoan Thanh!"
>> '@ | Set-Content tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
# Script : tong_hop.ps1
# Tac gia :  NGUYEN BAO HUY
# Ngay tao : 11-11-2026
Write-Host "Dang tao bao cao..."
"=== BAO CAO SU CO WEBSITE ===" > logs/tong_hop.txt
Get-Content logs/visit.log | Select-String "status=404" >> logs/tong_hop.txt
Get-Content logs/visit.log | Select-String "status=500" | Measure-Object >> logs/tong_hop.txt
Write-Host "Hoan Thanh!"

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [X] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [X] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [X] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | Network | logo.png | đổi tên logo-aquazone thành tên logo.png |
| 2 | Console | ERR_FILE_NOT_FOUND , Uncaught ReferenceError  | đổi tên file hình ảnh và đổi tên hienThiBangGia thành hienThiBangGiaVe    |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** đang chạy chương trình trên app.js 
- **Expected:** chương trình đọc lỗi file hình ảnh và lỗi chính tả trong app.js   
- **Actual:** đã kiểm tra sửa đổi tên file hình ảnh và ghi lại chính tả và thành công

- **Log:** Uncaught ReferenceError: hienThiBangGia is not defined

### Câu tìm kiếm Google

```text
site:stackoverflow "Uncaught ReferenceError: is not defined"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/ban_ve_thang_1.xlsx`, không cần ghi vào đây.
