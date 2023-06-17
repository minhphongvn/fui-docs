# Module

> **Module** trong một dự án FUI được định nghĩa như một trang được tạo ra nhằm thực hiện một chức năng nhất định trong dự án, có thể là một form để lấy thông tin từ người dùng, một trang báo cáo thống kê, landing page hoặc là bất cứ điều gì bạn có thể làm với một file HTML.

### Khởi tạo một module

Để tạo mới một module trong dự án bạn làm theo các bước sau:

1. Chọn dự án của bạn, nhấn vào biểu tượng ![](<../.gitbook/assets/Screen Shot 2023-02-06 at 01.46.20.png>) trên bảng.
2.  Ở form "Thêm mới" sẽ yêu cầu nhập các thông tin sau:\
    \
    \- **Domain**: Tên miền tuỳ chỉnh của bạn sở hữu (Không bắt buộc nhập).\
    \- **Module ID:** Tên phân biệt của module trong dự án (không được đặt trùng).\
    \- **Module name**: Tên mô tả của module (nên đặt rõ ràng để tiện phân biệt sau này khi nhiều module).\
    \- **HTML Only:** Nếu tích vào đồng nghĩa với việc bạn lựa chọn xây dựng module như một file HTML thuần và bỏ qua các chức năng của FUI (các chức năng của FUI sẽ không gọi được trong chế độ HTML Only này).\


    <figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
3. Sau khi điền xong các thông tin, bấm **"Thêm mới"** để tạo module.
4.  Module sau khi tạo thành công:\


    <figure><img src="../.gitbook/assets/Screen Shot 2023-02-06 at 02.17.12.png" alt=""><figcaption></figcaption></figure>
5.  Để xem module, có thể bấm vào ModuleName để xem trang vừa tạo.\
    \


    <figure><img src="../.gitbook/assets/Screen Shot 2023-02-06 at 08.50.44.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Nếu không có domain thì module sẽ có tên miền với cấu trúc sau:

**`https://fui.vn/[projectID]/[moduleID]`**
{% endhint %}

{% hint style="warning" %}
Lưu ý:&#x20;

* Nếu không tìm thấy module hãy tải lại trang và tìm module dựa vào Module ID.
* Ví dụ trên thuộc dự án Example có projectID là **ex**, thanh menu của module vừa tạo sẽ kế thừa lại menu đã được cấu hình của dự án.
{% endhint %}

### Cấu trúc module

Một module FUI được định nghĩa dưới dạng JSON với cấu trúc như sau:

```json
{
   "data": [],
   "watch": {},
   "controls": [],
   "set": {}
}
```

* **data**: Chứa các dữ liệu được định nghĩa. [Cách khai báo data](../data-va-khoi-lenh/data.md).
* **watch**: Sử dụng để theo dõi các giá trị dữ liệu bị thay đổi để thực hiện một lệnh nào đó. [Xem thêm](../data-va-khoi-lenh/watch.md).
* **controls**: Chứa cấu trúc giao diện người dùng của module. [Xem thêm.](broken-reference)
* **set**: Chứa các cấu hình chung của một module. [Xem thêm](broken-reference).

### Cấu hình module

{% hint style="warning" %}
Lưu ý:&#x20;

* Nếu dự án đã được cấu hình thì tất cả các module của dự án sẽ sử dụng chung một cấu hình của dự án.&#x20;
* Chỉ khi các cấu hình trên module được định nghĩa thì sẽ ghi đè lên cấu hình của dự án.
{% endhint %}

Để cấu hình dự án, bạn thực hiện các bước sau:

1. Ở màn hình UI Editor của module, chọn tab <img src="../.gitbook/assets/Screen Shot 2023-02-06 at 14.58.52.png" alt="" data-size="line">, chọn tab <img src="../.gitbook/assets/Screen Shot 2023-02-06 at 14.59.07.png" alt="" data-size="line"> bên trái.
2. Tuỳ chỉnh các giá trị phù hợp của các thuộc tính theo diễn giải phía dưới.

Cấu hình của một module (cũng tương tự project) được định nghĩa có cấu trúc gồm những thuộc tính sau đây:

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

Diễn giải:

* **ProjectName**: Tên mô tả của dự án.
* **title**: Tên tiều đề của module.
* **apiDomain**: Địa chỉ API chung của module.
* **login**: Trang xác thực người dùng của module, sẽ được chuyển đến nếu người dùng chưa xác thực.
* **logo**: Địa chỉ url của logo hiển thị trên thanh menu.
* **menucolor**: Màu chữ của thanh menu.
* **menubgcolor**: Màu của thanh menu.
* **userInfo**: API để lấy thông tin người dùng sau khi đã xác thực.
* **menu:** Mảng chứa cấu trúc menu của module
  * **name**: Tên hiển thị trên thanh menu.
  * **url**: Địa chỉ của menu.
  * **submenu**: Chứa những mục con của menu.
