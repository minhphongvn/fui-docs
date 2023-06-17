# f-button

## Giới thiệu

`f-button` là một component dùng để hiển thị button.

## Sử dụng

```json
{
    "el": "f-button",
    "attr": {
        "label": "Button",
        "action": {
            "FUN": "openWindow",
            "IN": {
                "id": "`windowId",
                "title": "Tiêu đề cửa sổ",
                "width": 800,
                "height": 600,
                "url": "`https://example.com"
            }
        }
    }
}
```

## Các thuộc tính

Vì kế thừa nên các thuộc tính của `f-button` cũng tương tự như [`v-btn`](https://v2.vuetifyjs.com/en/api/v-btn) của Vuetify. Tuy nhiên, `f-button` có thêm một số thuộc tính sau:

* `label` (string): Nội dung của button.
* `action` (object): Hành động khi click vào button. Để thực thi một khối lệnh bất kì.
