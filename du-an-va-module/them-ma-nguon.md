# Thêm mã nguồn

Đôi khi xây dựng module với những tính năng không được tích hợp sẵn thì việc sử dùng thêm mã nguồn hoặc thư viện Javascript là điều cần thiết để xây dựng các tính năng đặc biệt.

Để thêm một mã nguồn vào dự án (việc này có nghĩa là mã nguồn sẽ áp dụng cho toàn bộ dự án, tất cả các module trong dự án đều có thể gọi, tham chiếu đến mã nguồn này), chọn <img src="../.gitbook/assets/Screen Shot 2023-04-11 at 15.14.00.png" alt="" data-size="line"> bên góc phải màn hình (thêm mã nguồn vào từng module cũng vậy, bấm vào tab Import bên trái màn hình UI Editor), tiếp theo chọn <img src="../.gitbook/assets/Screen Shot 2023-04-11 at 15.17.33.png" alt="" data-size="line">, điền các thông tin vào form như dưới đây, sau đó bấm Thêm mới để hoàn thành:

<figure><img src="../.gitbook/assets/Screen Shot 2023-04-11 at 15.25.38.png" alt=""><figcaption></figcaption></figure>

**Chú giải:**

* **Sort:** Thứ tự ưu tiên của mã nguồn trong module
* **File Name:** Tên file mã nguồn hoặc địa chỉ của mã nguồn.
* **File Type:** Phụ thuộc vào File Name, nếu giá trị của File Name là một địa chỉ mã nguồn thì File Type sẽ là **link** và địa chỉ của mã nguồn sẽ được thêm vào module khi tải trang**,** nếu chọn File Type là **js** hoặc **css** thì một file js hoặc css sẽ được tạo ra để chúng ta có thể viết mã bên trong đó.

{% hint style="info" %}
Đối với **comp-link** là những thư viện, script, css đã được tích hợp sẵn trong FUI và được sử dụng bởi các **Fast Component** (các component có tiền tố là 'f-\*', ví dụ: 'f-date', 'f-button', 'f-time',...) nên không cần phải tạo mới.

Trong trường hợp này, sau khi đã khởi tạo control là F_ast Component_ xong, bạn có thể tải trang và phát hiện lỗi ở tab Console trình duyệt (thường là lỗi \[cái gì đó] is not defined), hãy chuyển sang phần Import của module "mà bạn đang xây dựng" (nhớ là module nhé, vì bạn có thể nhầm lẫn giữa import project và module), ở giao diện import này hãy bấm vào nút <img src="../.gitbook/assets/Screen Shot 2023-04-12 at 09.44.53.png" alt="" data-size="line"> để FUI cập nhật các thư viện mà module cần dùng.
{% endhint %}
