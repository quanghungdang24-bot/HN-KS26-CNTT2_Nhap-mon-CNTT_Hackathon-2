# BÀI LÀM – HACKATHON 02

- **Mã đề:** 10
- **Họ tên:** Đặng Quang Hưng
- **Lớp:** CNTT2
- **Link repository:**
- **Hệ điều hành (Windows/macOS):** macOS

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -aR
mv checklist_chuyen_nha.txt docs
mkdir backup
cp data/hop_dong_thang_10.xlsx backup
rm *.tmp
cd ./logs; ls; cd ..
ls -aR

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
.				.env				data				logs
..				bai_lam.md			docs				temp_010.tmp
.DS_Store			checklist_chuyen_nha.txt	evidence			web

./data:
.			..			hop_dong_thang_10.xlsx

./docs:
.	..

./evidence:
.	..

./logs:
.		..		request.log

./web:
.		..		app.js		images		index.html	style.css

./web/images:
.			..			logo-movefast.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
cat logs/request.log | grep "status=500" > logs/loi_500.txt

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-10-28 08:09:39 POST /api/dat-xe status=500
2026-10-28 08:13:50 POST /api/thanh-toan status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
cat logs/request.log | grep "status=404" | wc -l

```

```text
       4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
bash tong_hop.sh
cat logs/tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===
2026-10-28 08:28:45 GET /dat-xe-cu status=404
2026-10-28 08:41:29 GET /khuyen-mai-cu status=404
2026-10-28 08:50:02 GET /khuyen-mai-cu status=404
2026-10-28 09:05:46 GET /tin-tuc status=404
       6

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
| 1 | network | net::ERR_FILE_NOT_FOUND | Vào file `.html` sửa lại tên của logo ảnh |
| 2 | console | Uncaught ReferenceError: hienThiGoi is not defined |  Vào file `.js` sửa dòng cuối đúng tên đường dẫn |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Chào nhóm trưởng nhóm 2 tôi đnag gặp lỗi khi code html và js.
- **Expected:** Mong nhóm trưởng có thể giúp đỡ tìm và sửa lỗi 
- **Actual:** Bảng model không hiển thị dũe liệu, Trong tab console xuất hiện báo cáo lỗi này màu đỏ, khiến chức năng hiển thị trong bảng model không hoạt động
- **Log:** net::ERR_FILE_NOT_FOUND

### Câu tìm kiếm Google

```text
site:Stackoverflow "net::ERR_FILE_NOT_FOUND"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/hop_dong_thang_10.xlsx`, không cần ghi vào đây.
