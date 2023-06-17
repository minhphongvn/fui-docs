# Data

## Khai báo

Data của một module được định nghĩa trong thuộc tính "**data"** của cấu trúc module dưới dạng JSON.

Ở giao diện UI Editor của module để khai báo một data, chọn tab <img src="../.gitbook/assets/Screen Shot 2023-02-06 at 14.58.52 (1).png" alt="" data-size="line"> sau đó chọn <img src="../.gitbook/assets/Screen Shot 2023-02-06 at 15.29.04.png" alt="" data-size="line">, bắt đầu khởi tạo data ở đây, hoặc có thể chọn tab <img src="../.gitbook/assets/Screen Shot 2023-02-06 at 15.32.34.png" alt="" data-size="line"> và định nghĩa một data ở thuộc tính `data: []`

Dưới đây là ví dụ:

```json
// video
```

## Kiểu dữ liệu

Dưới đây là các kiểu dữ liệu thường được sử dụng và cách định nghĩa chúng trong FUI.

#### Chuỗi ký tự

```json
{
    "value": "Hello World"
}
```

{% hint style="warning" %}
Nếu giá trị trị chuỗi là một từ (không có khoảng trắng), ví dụ như: \
`{`&#x20;

&#x20;   `"value": "Ten"`

`}`\
`thì FUI sẽ hiểu giá trị đó là một biến dữ liệu.`\
\
``Để xử lí trường hợp này, thêm dấu ` hoặc '' vào giá trị như sau:``\
`{`&#x20;

&#x20;   ``"value": "`Ten"``

`}`

hoặc

`{`

&#x20;   `"value": "'Ten'"`

`}`
{% endhint %}
