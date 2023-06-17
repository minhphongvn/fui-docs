# Icons

Icon của FUI sử dụng thư viện [Material Design Icons](https://pictogrammers.com/library/mdi/).

## 1. Hiển thị icon

```json
{
    "el": "v-icon",
    "innerHTML": "mdi-account"
}
```

Icon được viết theo cấu trúc `mdi-<tên icon>`.

Ví dụ:

* `mdi-account` là icon tài khoản.
* `mdi-magnify` là icon kính lúp.

Tiền tố `mdi` là tên viết tắt của _**M**_aterial _**D**_esign _**I**_cons.

Bạn có thể tìm kiếm icon tại [đây](https://pictogrammers.com/library/mdi/). Hãy sử dụng các đầu mục bên trái của trang để lọc icon theo chủ đề để có kết quả tìm kiếm tốt nhất.

## 2. Các trường hợp thường sử dụng icon

### Tạo một nút đăng nhập:

```json
{
    "el": "v-btn",
    "attr": {
        "color": "primary",
        "dark": true
    },
    "innerHTML": [
        {
            "el": "v-icon",
            "attr": {
                "left": true
            },
            "innerHTML": "mdi-account"
        },
        {
            "el": "span",
            "innerHTML": "Đăng nhập"
        }
    ]
}
```

### Thêm icon vào một text field:

```json
{
    "el": "v-text-field",
    "attr": {
        "label": "Tìm kiếm",
        "append-icon": "mdi-magnify"
    }
}
```
