# Gửi, nhận dữ liệu

### Gửi, nhận dữ liệu

Để gửi dữ liệu sang một module khác có thể sử dụng **query string** với cặp `key=value` theo cấu trúc của ví dụ sau:

```markup
https://fui.vn/ex/demo-module?val1=123&val2=abc&...
```

Như ví dụ trên một biến data tên là **val1** mang giá trị 123 và **val2** mang giá trị "abc" được khởi tạo có thể sử dụng trong module mà bạn trỏ đến, như ví dụ trên thì module **"demo-module"** sẽ tự động khởi tạo 2 biến tên là **val1** và **val2** mang giá trị tương ứng.&#x20;

\
<mark style="color:red;">**\*Lưu ý**</mark>: Giá trị nhận trừ query params đều là chuỗi ký tự (string)
