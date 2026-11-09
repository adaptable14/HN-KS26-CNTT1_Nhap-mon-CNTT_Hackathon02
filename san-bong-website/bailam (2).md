# BÀI LÀM – HACKATHON 02

-   **Mã đề:** 01

-   **Họ tên:** Hà Duy Mạnh 

-   **Lớp:** 	CNTT1

-   **Link repository:**[https://github.com/adaptable14/HN-KS26-CNTT1_Nhap-mon-CNTT_Hackathon02/tree/main](https://github.com/adaptable14/HN-KS26-CNTT1_Nhap-mon-CNTT_Hackathon02/tree/main)

-   **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```Get-Location
Get-ChildItem -Force
Move-Item ghi_chu_ban_giao.txt docs/
New-Item -ItemType Directory -Name backup
Copy-Item data/dat_san_thang_10.xlsx backup/
Remove-Item temp_002.tmp
Set-Location logs
Get-ChildItem
Set-Location ..
Get-ChildItem -Recurse -Force

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)


```
san-bong-website
├── .env
├── .gitignore
├── .env.example
├── README.md
├── bai_lam.md
├── tong_hop.ps1
├── docs
│   └── ghi_chu_ban_giao.txt
├── data
│   └── dat_san_thang_10.xlsx
├── logs
│   ├── access.log
│   ├── loi_500.txt
│   └── tong_hop.txt
├── backup
│   └── dat_san_thang_10.xlsx
├── evidence
│   ├── network.png
│   └── console.png
└── web
    ├── index.html
    ├── style.css
    ├── app.js
    └── images
        └── logo-san-bong.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```
Select-String "status=500" logs/access.log 
```




### 2 dòng đầu tiên trong logs/loi_500.txt

```
 ForEach-Object { $_.Line } | Set-Content logs/loi_500.txt

```

### b) Lệnh đếm số dòng status=404 và kết quả

```
(Get-Content logs/access.log | Select-String "status=404" | Measure-Object).Count
```


## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```

.\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt


```text
=== BAO CAO SU CO WEBSITE ===
(Các dòng chứa status=404 lấy từ access.log)
(Số dòng chứa status=500)
```


## 4.5. [README.md](http://README.md) và bảo vệ thông tin bí mật

> [README.md](http://README.md), .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu [x] vào các mục đã làm để tự kiểm tra.

-   [x] [README.md](http://README.md): Heading 1, mô tả có **in đậm** và _in nghiêng_, bảng, code block, task list, blockquote

-   [x] .gitignore có dòng .env (tên file đúng, không có đuôi .txt)

-   [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
|---|---|---|---|
| 1 | Network | File images/logo.png không tải được | Sửa đường dẫn trong index.html thành images/logo-san-bong.png |
| 2 | Console | Lỗi ReferenceError: hienThiBangGia is not defined trong app.js | Sửa lời gọi hàm hienThiBangGia() thành hienThiBangGiaSan() |


### Báo cáo lỗi gửi trưởng nhóm
-   **Context:** Em đang kiểm tra website đặt sân bóng mini trên Chrome bằng DevTools. Khi mở trang web, em phát hiện bảng giá không hiển thị dữ liệu.
    
-   **Expected:** Bảng giá phải hiển thị đầy đủ thông tin các loại sân và giá thuê theo giờ.
    
-   **Actual:** Bảng giá không hiển thị dữ liệu trên trang web.
    
-   **Log:**

### Câu tìm kiếm Google


```
site:stackoverflow.com "THÔNG BÁO LỖI TRONG CONSOLE"
```


## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file data/dat_san_thang_10.xlsx, không cần ghi vào đây.
