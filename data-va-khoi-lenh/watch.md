# Watch

## 1. Giới thiệu

Watch là một thành phần cấu trúc của một trang FUI dùng để theo dõi sự thay đổi của một biến, một thuộc tính của một biến, một phần tử của một mảng, hoặc một thuộc tính của một phần tử trong một mảng.

## 2. Cấu trúc

```json
{
    "data": [
        {
            "count": 0
        },
        {
            "person": {
                "name": "John",
                "age": 20
            }
        }
    ],
    "watch": {
        "count": {
            // Thực thi khối lệnh khi giá trị của biến count thay đổi
        },
        "person.age": {
            "MESS": "person.age > 18 ? 'Đủ tuổi' : 'Chưa đủ tuổi'"
        }
    }
}
```