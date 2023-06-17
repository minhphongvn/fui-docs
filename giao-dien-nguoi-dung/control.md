# Control

{% hint style="info" %}
Giao diện FUI được xây dựng bằng HTML và [Vuetify 2](https://v2.vuetifyjs.com/en/) Component dưới dạng cấu trúc JSON
{% endhint %}

### Cấu trúc control

Dưới đây là ví dụ để tạo một giao diện nút bấm (Button):

<div align="left">

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

</div>

Với giao diện nút bấm như trên trong FUI được thể hiện dưới dạng cấu trúc như sau:

```json
{
   "el": "v-btn",
   "col": {},
   "attr": {
      "class": "rounded-xl",
      "color": "primary",
      "depressed": "",
      "v-on:click": "() => alert('abc')"
   },
   "innerHTML": "<v-icon left>mdi-account</v-icon> Click Me"
   "w": 6
}
```

Còn đây là cách thể hiện ở HTML

```html
<v-flex class="px-2" xs12 md6>
    <v-btn class="rounded-xl" color="primary" depressed @click="() => alert('abc')">
        <v-icon left>mdi-account</v-icon> Click Me
    </v-btn>
</v-flex>
```

#### Cấu trúc của một control gồm:

* **el:** Tên của một "html tag" hay [component](https://vuetifyjs.com/en/components/alerts) của Vuetify (v-text-field, v-btn,...) hoặc đối tượng Vue component được xây dựng thêm (f-table, f-button,...).
* **col:** Thuộc tính của v-flex, vì các control được bao trong một v-flex. Tìm hiểu [thuộc tính v-flex](https://vuetifyjs.com/en/api/v-flex/) và [Flex Layout](https://vuetifyjs.com/en/styles/flex/)
* **attr:** Các thuộc tính props (bao gồm cả sự kiện [event](https://vi.vuejs.org/v2/guide/events.html)) của một component Vuetify hoặc của hệ thống. Ví dụ v-btn trên có những thuộc tính sau:
* ```json
  {
      "class": "rounded-xl",
      "color": "primary",
      "depressed": "",
      "v-on:click": "() => alert('abc')"
  }
  ```
* **innerHTML:** Bao gồm chuỗi HTML hoặc mảng các cấu trúc control bên trong của control hiện tại.
* **w:** Độ rộng của một control được xác định bởi số cột mà control sẽ chiếm bên trong hệ thống lưới và như chúng ta đã biết một hệ thống lưới được quy ước là 12 cột. Tìm hiểu rõ hơn tại đây [Vuetify Grid System](https://vuetifyjs.com/en/components/grids) và [Flex Layout](https://vuetifyjs.com/en/styles/flex)
