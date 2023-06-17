# Khối lệnh

Mỗi khối lệnh được tạo ra để thực thi một hành động nào đó, có thể là gọi API, gọi một hàm, hoặc thực hiện một phép tính nào đó.

## Gọi một hàm

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

## Lấy dữ liệu từ API

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

### Callback

Nếu bạn muốn gọi lại một hàm sau khi gọi API thành công thì bạn có thể sử dụng cấu trúc sau:

```json
{
    "API": "https://api.example.com/api/v1/addTodo",
    "METHOD": "POST",
    "IN": {
        "title": "Mua vé số",
        "status": "finished"
    },
    "OUT": "result",
    "CALLBACK": {
        "FUN": "addTodoSuccess",
        "IN": {
            "result": "result"
        }
    }
}
```

## Câu lệnh điều kiện

Để thực hiện một câu lệnh điều kiện bạn có thể sử dụng cấu trúc sau:

```json
{
    "IF": "list.length > 0",
    "THEN": {
        // thực hiện một khối lệnh
    },
    "ELSE": {
        // thực hiện một khối lệnh
    }
}
```

## Thông báo trước khi gọi một khối lệnh

Nếu bạn muốn hiển thị thông báo cho người dùng trước khi gọi một khối lệnh thì bạn có thể sử dụng cấu trúc sau:

```json
{
    "CONFIRM": "Bạn có muốn thêm không?",
    "API": "https://api.example.com/api/v1/addTodo",
    "METHOD": "POST",
    "IN": {
        "title": "Mua vé số",
        "status": "finished"
    },
    "OUT": "result",
    "CALLBACK": {
        "FUN": "addTodoSuccess",
        "IN": {
            "result": "result"
        }
    }
}
```

## Thông báo nổi (Toast)

Để hiển thị một thông báo nổi bạn có thể sử dụng cấu trúc sau:

```json
{
    "MESS": "Thêm thành công"
}
```

Ví dụ sau khi gọi API thành công:

```json
{
    "API": "https://api.example.com/api/v1/addTodo",
    "METHOD": "POST",
    "IN": {
        "title": "Mua vé số",
        "status": "finished"
    },
    "OUT": "result",
    "CALLBACK": {
        "FUN": "addTodoSuccess",
        "IN": {
            "result": "result"
        }
    },
    "MESS": "Thêm thành công"
}
```

## Gọi một khối lệnh

Để gọi một khối lệnh bạn có thể sử dụng cấu trúc sau:

```json
{
    "CALL": "addTodo"
}
```

## Thực thi một đoạn mã Javascript

Để thực thi một đoạn mã Javascript bạn có thể sử dụng cấu trúc sau:

```json
{
    "EXE": "console.log('Hello world')"
}
```
