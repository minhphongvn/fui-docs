# Bố cục trang

## 1. Giới thiệu

Bố cục trang (Layout) là một thành phần cấu trúc của một trang FUI dùng để quy định bố cục giao diện của một trang. Bố cục trang được định nghĩa trong một file JSON với cấu trúc như sau:


```json
{
    "controls": [
      {
         "prop": "fluid grid-list-md",
         "rows": [
            {
               "prop": "",
               "cols": [
                  {
                     "el": "f-com",
                     "col": {},
                     "attr": {}
                  }
               ]
            }
         ]
      },
      {
         "prop": "fluid grid-list-md",
         "rows": [
            {
               "prop": "",
               "cols": [
                  {
                     "el": "f-com",
                     "col": {},
                     "attr": {}
                  }
               ]
            }
         ]
      }
   ]
}
```

## 2. Cấu trúc

### 2.1. Cấu trúc chung

Bố cục trang được định nghĩa bởi một mảng các thành phần `controls`. Mỗi thành phần của `controls` có cấu trúc như sau:

```json
{
    "prop": "fluid grid-list-md",
    "rows": [
        {
            "prop": "",
            "cols": [
                {
                    "el": "f-com",
                    "col": {},
                    "attr": {}
                }
            ]
        }
    ]
}
```

Trong đó:

- `prop`: là một chuỗi, quy định kiểu bố cục của thành phần. Chứa các class Vuetify để quy định kiểu bố cục.
- `rows`: là một mảng các thành phần `row`. Mỗi thành phần của `rows` là có cấu trúc như sau:

```json
{
    "prop": "",
    "cols": [
        {
            "el": "f-com",
            "col": {},
            "attr": {}
        }
    ]
}
```

Trong đó:

- `prop`: là một chuỗi, quy định kiểu bố cục của thành phần. Chứa các class Vuetify để quy định kiểu bố cục.
- `cols`: là một mảng các thành phần `col`. Mỗi thành phần của `cols` là các `control` được định nghĩa trong [Cấu trúc của một control](/docs/giao-dien-nguoi-dung/control).
