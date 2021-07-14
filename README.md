<p align="center">
	<img src="https://res.cloudinary.com/dml8e1w0z/image/upload/v1625188482/oop-learning-helper/color_tnvl21.png" width="100px" height="auto" />
	<p align="center">
	<strong>Website:</strong>
	<a href="https://oop-learnee.herokuapp.com/">OOPForLearnee</a>
	</p>
</p>
<h1 align="center">Ứng dụng Web tích hợp với Messenger Chatbothỗ trợ môn học OOP
</h1>

# Nội dung chính
- [Mô tả](#description)
- [Hướng dẫn cài đặt](#setup-guide)
  * [1. Cài đặt và cấu hình Frontend](#frontend-setup)
  * [2. Cấu hình và cài đặt Backend](#backend-setup)
  * [3. Cấu hình chatbot](#chatbot-setup)
- [Hướng dẫn sử dụng ứng dụng](#usage-guide)
  * [1. Các chức năng cơ bản của ứng dụng Web](#web-features)
  * [2. Các chức năng quản lí](#web-management-features)
  * [3. Hướng dẫn sử dụng Chatbot](#chatbot-usage-guide)
- [Thành viên đóng góp](#contributors)


# <a name="description">Mô tả</a>

Tại **OOPForLearnee** bạn có thể học những bài học OOP từ cơ bản đến nâng cao và có lộ trình được sắp xếp dựa trên chủ đề. Ngoài ra người dùng có thể tương tác với chatbot để được hỗ trợ và cung cấp các thông tin liên quan đến các khái niệm OOP, thông tin bài học, ...

# <a name="setup-guide">Hướng dẫn cài đặt</a>

## <a name="frontend-setup">1. Cài đặt và cấu hình Frontend</a>

### Clone project:
```
git clone https://github.com/minhnguyenduy99/EasyOOP-frontend.git
```
### Cài đặt package:
```
npm install
```

### Cấu hình biến môi trường
Tạo **2** file biến môi trường ```.env.development.local``` (dành cho development) và ```.env.production.local```(dành cho production). Mẫu file environmnent co thể xem tại [```frontend.env.sample```](https://github.com/minhnguyenduy99/OOPForLearnee/blob/main/environments/frontend.env.sample).

Bạn có thể tạo các file biến môi trường với các mode khác nhau.  Quy định đặt tên có thể xem tại: https://cli.vuejs.org/guide/mode-and-env.html

### Khởi động server:
```
npm run serve
```
Server mặc định sẽ chạy tại http://localhost:8080 

### Build production
```
npm run build
```

## <a name="backend-setup">2. Cấu hình và cài đặt Backend</a>
### Clone project:
```
git clone https://github.com/minhnguyenduy99/EasyOOP_Backend.git
```
### Cài đặt package:
```
npm install
```
### Cấu hình biến môi trường
- Tạo file biến môi trường. Mẫu file environmnent có thể xem tại [```backend.env.sample```](https://github.com/minhnguyenduy99/OOPForLearnee/blob/main/environments/backend.env.sample).
- Cập nhật tên file môi trường vao file ```app.module.ts``` như sau:
![](https://i.im.ge/2021/07/14/2lvCS.png)

### Khởi động server:
Chạy với chế độ **reload**
```
npm run start:dev
```
Hoặc chế độ bình thường
```
npm run start
```

### Build production
```
npm run build
```

## <a name="chatbot-setup">3. Cấu hình chatbot</a>

### Clone project:
```
git clone https://github.com/LichND/NLP.git
```
### Cài đặt package:
```
npm install
```

### Thiết lập đầu vào
Tại thư mục input có 2 folder (topic và type) và file mix kèm, chi tiết:
- Folder topic:
  * Tên file không được chứa extensions
  * Tên file dùng làm tag name
  * Nội dung file gồm các keyword liên quan đến tag name, phân biệt nhau bởi ký tự endline (```\n``` hoặc ```\r\n```)
- Folder type
  * Tên file không được chứa extensions
  * Tên file dùng làm tag name
  * Nội dung file gồm các mẫu câu liên quan đến tag name, phân biệt nhau bởi ký tự endline (```\n``` hoặc ```\r\n```)
  * Nếu mẫu câu có liên quan đến một topic nào đó, thay phần liên quan bằng kí tự ```%s```
- File mix
  * Dùng để thay thế và trộn các mẫu câu có dùng topic (có chứa kí tự ```%s```)
  * Nội dung file là &lt;tên tag 1&gt;+&lt;tên tag 2&gt;+..., giữa các tag là dấu ```+```, phân biệt nhau bởi ký tự endline (```\n``` hoặc ```\r\n```)

### Make data
```
npm run data
```

### Train model
```
npm run train
```

### Test lại sau train (tùy chọn)
```
npm run test
```
hoặc
```
npm run test <nội dung test>
```

# Áp dụng train model mới
Copy toàn bộ các file trong thư mục ```./out``` của train model sang thư mục ```./src/lib/nlp/out``` của backend

Chú ý: file ```tag.ts``` sẽ cho output là các string tag theo mặc định input, nếu có sửa sang custom tag thì khi copy nhớ sửa lại theo custom tag cho đúng.

# <a name="usage-guide">Hướng dẫn sử dụng ứng dụng</a>

## <a name="web-features">1. Các chức năng cơ bản của ứng dụng Web</a>

### [Trang chủ](https://i.im.ge/2021/07/14/2lcAW.png)
### [Tìm kiếm](https://i.im.ge/2021/07/14/2lgp0.png)
### [Chi tiết bài viết](https://i.im.ge/2021/07/14/2lb7r.png)
### [Làm bài test](https://i.im.ge/2021/07/14/2l3Gm.png)
### [Thông tin cá nhân](https://i.im.ge/2021/07/14/2lxbf.png)
### [Kết quả bài test](https://i.im.ge/2021/07/14/2lEi1.png)

## <a name="web-management-features">2. Các chức năng quản lí</a>
<p align="center">ĐANG CẬP NHẬT</p>

## <a name="chatbot-usage-guide">3. Hướng dẫn sử dụng Chatbot</a>

### Bước 1: Truy cập [fanpage](https://www.facebook.com/EasyOOP/)
### Bước 2: Chọn Gửi tin nhắn
![](https://i.im.ge/2021/07/14/2rWJY.png)
### Bước 3: Bắt đầu tương tác với chatbot thôi!
![](https://i.im.ge/2021/07/14/2rffC.png)

# <a name="contributors">Thành viên đóng góp</a>

- Nguyễn Duy Minh - [minhnguyenduy99](https://github.com/minhnguyenduy99)
- Nguyễn Du Lịch - [LichND](https://github.com/LichND)
