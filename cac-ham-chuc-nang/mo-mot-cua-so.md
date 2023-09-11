# Mở một cửa sổ

## 1. Cấu trúc

```json
{
    "FUN": "openWindow",
    "IN": {
        "id": "`windowId",
        "title": "Tiêu đề cửa sổ",
        "width": 800,
        "height": 600,
        "url": "`https://example.com",
        "onclose": {
            "MESS": "Đã đóng cửa sổ"
        }
    }
}
```

## 2. Các thuộc tính

`id` (string): ID của cửa sổ, dùng để phân biệt các cửa sổ với nhau.

`title` (string): Tiêu đề của cửa sổ.

`width` (number): Chiều rộng của cửa sổ.

`height` (number): Chiều cao của cửa sổ.

`url` (string): Đường dẫn của cửa sổ.

`onclose`(object): Khối lệnh được chỉ thị thực thi khi đóng cửa sổ.
