# Data

## Khai báo

Data của một module được định nghĩa trong thuộc tính "**data"** của cấu trúc module dưới dạng JSON.

Ở giao diện UI Editor của module để khai báo một data, chọn tab <img src="../.gitbook/assets/Screen Shot 2023-02-06 at 14.58.52 (1).png" alt="" data-size="line"> sau đó chọn <img src="../.gitbook/assets/Screen Shot 2023-02-06 at 15.29.04.png" alt="" data-size="line">, bắt đầu khởi tạo data ở đây, hoặc có thể chọn tab <img src="../.gitbook/assets/Screen Shot 2023-02-06 at 15.32.34.png" alt="" data-size="line"> và định nghĩa một data ở thuộc tính `data: []`

## Cấu trúc

Một data được định nghĩa bởi một JSON Object, mỗi data sẽ có một tên duy nhất để phân biệt với các data khác. Tên của data được định nghĩa trong thuộc tính `name` của JSON Object.

```json
{
    "data": [
        {
            "name": "data1",
            "value": "value1"
        }
    ]
}
```

## Các kiểu dữ liệu

### String

Kiểu dữ liệu `String` được định nghĩa bởi một chuỗi ký tự, được bao bởi dấu nháy gán tiền tố \` nếu chuỗi ký tự không chứa khoảng trắng.

```json
{
    "data": [
        {
            "text": "`ABC",
            "value": "`XYZ"
        }
    ]
}
```

### Number

Kiểu dữ liệu `Number` được định nghĩa bởi một số, có thể là số nguyên hoặc số thực.

```json
{
    "data": [
        {
            "data1": 2099
        },
        {
            "value": "data1", // value = 2099 
            "count": 1
        }
    ]
}
```

### Boolean

Kiểu dữ liệu `Boolean` được định nghĩa bởi một giá trị `true` hoặc `false`.

```json
{
    "data": [
        {
            "isChecked": true
        },
        {
            "isFinished": "isChecked", // isFinished = true
        }
    ]
}
```

### Array

Kiểu dữ liệu `Array` được định nghĩa bởi một mảng các giá trị, mỗi giá trị có thể là một kiểu dữ liệu bất kỳ.

```json
{
    "data": [
        {
            "list": [1, 2, 3]
        },
        {
            "value": "list", // value = [1, 2, 3]
            "count": "list.length" // count = 3
        }
    ]
}
```

### Object

Kiểu dữ liệu `Object` được định nghĩa bởi một JSON Object, mỗi thuộc tính của Object có thể là một kiểu dữ liệu bất kỳ.

```json
{
    "data": [
        {
            "person": {
                "name": "John",
                "age": 30
            }
        },
        {
            "value": "person", // value = { "name": "John", "age": 30 }
            "name": "person.name" // name = "John"
        }
    ]
}
```

### Khối lệnh

Kiểu dữ liệu khối lệnh được định nghĩa bởi một khối lệnh, mỗi khối lệnh được tạo ra để thực thi một hành động nào đó, có thể là gọi API, gọi một hàm, hoặc thực hiện một phép tính nào đó.

Ví dụ khai báo một khối lệnh gọi API lấy danh sách topic:

```json
{
    "data": [
        {
            "getListTopic": {
                "API": "https://api.example.com/api/v1/topics",
                "METHOD": "GET",
                "OUT": "topicList",
            }
        }
    ]
}
```

Hoặc khởi tạo một hàm mở cửa sổ mới:

```json
{
    "data": [
        {
            "openWindowA": {
                "FUN": "openWindow",
                "IN": {
                    "id": "`windowA",
                    "title": "`Cửa sổ A",
                    "url": "`https://example.com/windowA",
                    "width": 800
                }
            }
        }
    ]
}
```
