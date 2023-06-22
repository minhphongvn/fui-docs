# f-table

## Giới thiệu

`f-table` là một component dùng để hiển thị dữ liệu dạng bảng. Component này được xây dựng dựa trên [`v-data-table`](https://v2.vuetifyjs.com/en/components/data-tables). Tuy nhiên, `f-table` được tuỳ biến để có thêm một số tính năng phục vụ cho việc xây dựng và quản lý đơn giản hơn như:

* Tạo control tuỳ biến cho từng cột một cách đơn giản nhất (định nghĩa ngay trên headers). Ví dụ: tạo control để nhập, sửa, thay đổi trạng thái trực tiếp trên bảng, tạo control để thực thi một lệnh bất kì trên dòng dữ liệu tương ứng,...
* Cho phép xuất dữ liệu dạng bảng ra file Excel.
* Tạo giao diện thêm mới, sửa, xóa dữ liệu trực tiếp ngay trên bảng.
* Tự động tạo các control phục vụ cho việc tìm kiếm, lọc dữ liệu.
* Thêm tiêu đề bảng nhanh chóng.

## Tạo bảng

Chúng ta sẽ tạo bảng theo cấu trúc như sau:

{% tabs %}
{% tab title="Control" %}
{% code lineNumbers="true" fullWidth="false" %}
```json
{
  "el": "f-table",
  "col": {},
  "attr": {
    "excel": true,
    "label": "Danh sách sinh viên",
    ":items-per-page": -1,
    ":fixed-header": true,
    ":height": "window.innerHeight-300",
    ":show-select": true,
    ":fixed-cols": 2,
    ":mobile-breakpoint": 600,
    ":items": "DanhSachSV",
    "item-key": "MSSV",
    ":update-form": [
      {
        "el": "v-text-field",
        "attr": {
          "v-model": "Ho",
          "label": "Họ"
        },
        "w": 6
      },
      {
        "el": "v-text-field",
        "attr": {
          "v-model": "Ten",
          "label": "Tên"
        },
        "w": 6
      },
      {
        "el": "f-date",
        "attr": {
          "v-model": "NgaySinh",
          "label": "Ngày sinh",
          "date-add": 0
        },
        "w": 4
      },
      {
        "el": "v-select",
        "attr": {
          "v-model": "GioiTinh",
          "label": "Giới tính",
          ":items": "vueData.Genders"
        },
        "w": 4
      },
      {
        "el": "v-text-field",
        "attr": {
          "v-model": "Lop",
          "label": "Lớp"
        },
        "w": 4
      },
      {
        "el": "v-checkbox",
        "attr": {
          "v-model": "NoHocPhi",
          "color": "primary",
          "label": "Nợ học phí"
        }
      }
    ],
    ":headers": [
      {
        "text": "MSSV",
        "value": "MSSV"
      },
      {
        "text": "Họ Tên",
        "value": "HoTen",
        "el": "span",
        "innerHTML": "{{item.Ho}} {{item.Ten}}"
      },
      {
        "text": "Giới tính",
        "align": "center",
        "value": "GioiTinh",
        "el": "span",
        "innerHTML": "{{vueData.Genders[item.GioiTinh].text}}"
      },
      {
        "text": "Ngày sinh",
        "align": "center",
        "value": "NgaySinh",
        "el": "t-time",
        "attr": {
          "format": "DD/MM/yyyy"
        }
      },
      {
        "text": "Lớp",
        "align": "center",
        "value": "Lop"
      },
      {
        "text": "Nợ học phí",
        "align": "center",
        "value": "NoHocPhi",
        "el": "span",
        "innerHTML": "{{item.NoHocPhi?'Nợ':'Không nợ'}}"
      },
      {
        "text": "Chức năng",
        "value": "ctrl-update",
        "align": "center"
      }
    ],
    ":update-api": {
      "default-item": {},
      "new": {
        "DanhSachSV": "[...DanhSachSV, {...item, MSSV:DanhSachSV[DanhSachSV.length-1].MSSV*1+1}]"
      },
      "edit": {
        "DanhSachSV": "DanhSachSV.map(it => it.MSSV == item.MSSV ? {...it,...item} : it)"
      },
      "delete": {
        "DanhSachSV": "DanhSachSV.filter(it=>it.MSSV != item.MSSV)"
      }
    }
  }
}
```
{% endcode %}
{% endtab %}

{% tab title="Data" %}
{% code lineNumbers="true" %}
```json
{
  "DanhSachSV": [
    {
      "MSSV": "123000123",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000124",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000125",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000126",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000127",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000128",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000129",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000130",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000131",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000132",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    },
    {
      "MSSV": "123000133",
      "Ten": "Feng",
      "Ho": "Nguyễn Minh",
      "NgaySinh": "01/02/2003",
      "Lop": "23CT113",
      "GioiTinh": 0,
      "NoHocPhi": false
    }
  ]
}
```
{% endcode %}
{% endtab %}
{% endtabs %}

Đây là giao diện của bảng sau khi tạo:

<figure><img src="../../../.gitbook/assets/Screen Shot 2023-06-22 at 09.59.54.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Screen Shot 2023-06-22 at 10.00.21.png" alt=""><figcaption></figcaption></figure>

## Các thuộc tính

Vì kế thừa nên các thuộc tính của `f-table` cũng tương tự như [`v-data-table`](https://v2.vuetifyjs.com/en/api/v-data-table) của Vuetify. Tuy nhiên, `f-table` có thêm một số thuộc tính sau:

| Tên thuộc tính | Kiểu dữ liệu | Mặc định | Mô tả                               |
| -------------- | ------------ | -------- | ----------------------------------- |
| items          | Array        | `[]`     | Dữ liệu                             |
| item-key       | String       | `''`     | Thuộc tính làm khóa cho mỗi dòng    |
| headers        | Array        | `[]`     | Cấu hình hiển thị cho mỗi cột       |
| excel          | Boolean      | `false`  | Cho phép xuất dữ liệu ra file excel |
| label          | String       | `''`     | Tiêu đề của bảng                    |
| show-select    | Boolean      | `false`  | Hiển thị cột chọn                   |
| update-form    | Array        | `[]`     | Cấu hình form cập nhật dữ liệu      |
| update-api     | Object       | `{}`     | Cấu hình API cập nhật dữ liệu       |
| fixed-cols     | Number       | `0`      | Số cột cố định                      |
| fixed-header   | Boolean      | `true`   | Cố định header                      |
| height         | Number       | `0`      | Chiều cao của bảng                  |
| items-per-page | Number       | `5`      | Số dòng trên một trang              |
