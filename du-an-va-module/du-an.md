# Dự án

### Cấu trúc dự án

Một dự án FUI chứa nhiều module (trang) thực hiện một nhiệm vụ nhất định trong dự án. Các module có thể [tương tác dữ liệu và có quan hệ](broken-reference) với nhau.

<figure><img src="../.gitbook/assets/wframe0.png" alt=""><figcaption></figcaption></figure>

### Cấu hình dự án

Để cấu hình dự án, bạn thực hiện các bước sau:

1. Ở màn hình dự án, nhấn vào nút <img src="../.gitbook/assets/Screen Shot 2023-02-06 at 14.51.08.png" alt="" data-size="line">&#x20;
2. Một cửa sổ mới được mở ra với cấu trúc cấu hình của dự án.
3. Tuỳ chỉnh các giá trị phù hợp của các thuộc tính theo diễn giải phía dưới.

{% hint style="warning" %}
Cấu hình của project sẽ được áp dụng cho tất cả các module của nó. Ví dụ: thanh danh mục menu, địa chỉ API,.... sẽ được dùng chung với tất cả các module của nó.
{% endhint %}

Cấu hình của một project được định nghĩa có cấu trúc gồm những thuộc tính sau đây:

```json
{
  "ProjectName": "Tuyển sinh",
  "title": "Chương trình đại sứ",
  "apiDomain": "https://api.fui.vn/",
  "login": "https://login.fui.vn/",
  "menubgcolor": "indigo",
  "menucolor": "yellow--text",
  "logo": "https://fui.vn/images/fastUI_White.png",
  "userInfo": "https://api.fui.vn/acc/UserInfo",
  "menu": [
    {
      "name": "Giới thiệu",
      "url": "/gioi-thieu"
    },
    {
      "name": "Quản lý",
      "submenu": [
        {
          "name": "Danh sách đại sứ",
          "url": "/danhsach-daisu"
        },
        {
          "name": "Danh sách học sinh",
          "url": "/danhsach-hocsinh"
        }
      ]
    }
  ]
}
```

Diễn giải:&#x20;

{% hint style="info" %}
Để ẩn thanh menu `"menu": false`

Chỉ ẩn menu vẫn hiển thị thanh`"menu": []`

Trang không cần đăng nhập `"login": false`
{% endhint %}

<table><thead><tr><th width="229.33333333333334">Thuộc tính</th><th>Kiểu dữ liệu</th><th>Mô tả</th></tr></thead><tbody><tr><td><strong>ProjectName</strong></td><td>String</td><td>Tên mô tả của project.</td></tr><tr><td><strong>title</strong></td><td>String</td><td>Tên tiều đề.</td></tr><tr><td><strong>apiDomain</strong></td><td>String</td><td>Địa chỉ API.</td></tr><tr><td><strong>login</strong></td><td>String, Boolean</td><td>Trang xác thực người dùng của project, sẽ được chuyển đến nếu người dùng chưa xác thực.</td></tr><tr><td><strong>menubgcolor</strong></td><td>String</td><td>Màu của thanh menu.</td></tr><tr><td><strong>menucolor</strong></td><td>String</td><td>Màu chữ của thanh menu.</td></tr><tr><td><strong>logo</strong></td><td>String</td><td>Địa chỉ url của logo hiển thị trên thanh menu.</td></tr><tr><td><strong>userInfo</strong></td><td>String</td><td>API để lấy thông tin người dùng sau khi đã xác thực.</td></tr><tr><td><strong>menu</strong></td><td>Array, Boolean</td><td>Mảng chứa cấu trúc menu của project.<br>Trong đó:<br>   - <strong>name</strong>: Tên hiển thị trên thanh menu.<br>   - <strong>url</strong>: Địa chỉ của menu.<br>   - <strong>submenu</strong>: Chứa những mục con của menu.<br></td></tr></tbody></table>
