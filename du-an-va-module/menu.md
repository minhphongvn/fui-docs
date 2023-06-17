# Menu

FUI cung cấp phương pháp xây dựng một menu chuẩn hoá cho toàn bộ dự án và từng module, giúp người dùng khởi tạo menu một lần duy nhất và hiển thị ở tất cả các trang.

### Cấu trúc menu

```json
"menu": [
  {
    "name": "Hướng dẫn",
    "submenu": [
      {
        "name": "Tạo data",
        "url": "/ex/data"
      }
    ]
  },
  {
    "name": "Tool",
    "submenu": [
      {
        "name": "Build header",
        "url": "/ex/buildheader"
      }
    ]
  }
]
  
```

### Tạo menu

#### Trong dự án

Menu được cấu hình trong dự án sẽ được áp dụng cho toàn bộ các module của dự án.

#### Trong module

Menu được cấu hình trong module sẽ thay thế cho module của dự án (nếu có).
