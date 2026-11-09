## 1. Báo cáo phân tích (I/O)

-   Input:  sửa code và nhấn `Ctrl + S`.
    
-   Process: File được lưu vào SSD Local, sau đó phần mềm Cloud tự động đồng bộ file lên đám mây.
    
-   Output: Khi đồng bộ thành công, file xuất hiện dấu tích xanh, báo hiệu dữ liệu đã được đồng bộ.
    

## 2. Sơ đồ tổ chức thư mục Cloud
 ```Startup-Project/
├── Code/       (Mã nguồn)
├── Docs/       (Tài liệu)
├── Assets/     (Hình ảnh, tài nguyên)
└── .gitignore  (Loại trừ node_modules) cho sơ đồ này ko bị lỗi trong md
```

## 3. Thiết kế Hybrid Workflow

-   Local: Lưu và chạy code trên SSD để xử lý nhanh.
    
-   Cloud: Tự động đồng bộ các file trong `Code`, `Docs`, `Assets` để bảo vệ dữ liệu.
    
-   Files On-Demand: Chỉ tải file về máy khi cần sử dụng, giúp tiết kiệm dung lượng ổ cứng.
    
-   Xử lý `node_modules`: Loại trừ thư mục này khỏi đồng bộ, giữ lại `package.json` và `package-lock.json` để cài đặt lại thư viện khi cần.
