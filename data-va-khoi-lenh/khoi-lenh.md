# Khối lệnh

### Gọi một hàm

Ví dụ bạn có một hàm sau:

```javascript
function add({a, b}) {
    return a + b
}
```

Khi gọi hàm ở FUI sẽ sử dụng cấu trúc sau.

```json
{
    "FUN": "add" // Tên hàm đã khởi tạo,
    "IN": {      // Tham số của hàm.
        "a": 3,
        "b": 5
    },
    "OUT": "result" // Gán kết quả cho biến khi hàm trả về giá trị.
}
```

Bạn có thể thấy cấu trúc gọi hàm ở ví dụ bên trên được chia thành 3 phần khá là tường minh. Nó cũng tương tự khi bạn viết như này với Javascript:

```javascript
const result = add({a: 3, b: 5})
```

### Lấy dữ liệu từ API&#x20;

#### Cấu trúc

Ví dụ bạn có một API để lấy data như sau:

```
https://api.example.com/api/v1/addTodo
```

Khi gọi API ở FUI chúng ta sẽ có cấu trúc như sau:

```json
{
    "API": "https://api.example.com/api/v1/addTodo",
    "METHOD": "POST",
    "IN": {
        "title": "Mua vé số",
        "status": "finished"
    },
    "OUT": "result"
}
```

#### Gọi lại (callback)



