---
title: "Khởi tạo Lambda function"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 7.2.1. </b> "
---

# WebSocket Handler

Tại trang console AWS, tìm kiếm dịch vụ `Lambda` và tiến hành khởi tạo một **Lambda function** mới.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image.png)

Tiếp theo, tạo một **Lambda function** chạy `Node.js` version ***20***:

- Đặt tên cho **Lambda function**.
- Chọn Runtime là Node.js 20.
- Nhấn **Create function** để hoàn tất.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%201.png)

Source code được lưu trong repository GitHub đã cung cấp trước đó. Bạn truy cập vào đây để xem:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%202.png)

Dán source code của bạn vào ô chỉnh sửa:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%203.png)

### Cấu hình biến môi trường

Tiếp theo, cấu hình biến môi trường cho **Lambda function** của bạn để nó hoạt động chính xác.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%204.png)

Tạo các biến môi trường như sau:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%205.png)

### Lấy WebSocket Link

Trong mục Stage của API, bạn tiến hành sao chép URL của stage để gán vào biến môi trường.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%206.png)

Sau khi lấy được link, dán vào biến môi trường:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%207.png)

- Nhấn **Save** để lưu lại cấu hình.

Quay lại mục code, thực hiện deploy **Lambda function** đã tạo.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%208.png)

Chuyển sang bước tiếp theo.

### Chỉnh sửa Role

Tại giao diện thiết lập của Lambda, chọn:

**Configuration** → **Permissions** → *Role*

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%209.png)

Bạn sẽ thấy role mặc định của Lambda:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2010.png)

Nhấp chọn role này và chỉnh sửa thêm statement sau:

```json
"Statement": [
		{
			"Action": "execute-api:ManageConnections",
			"Resource": "*",
			"Effect": "Allow"
		}
	]
```

- Nhấn **Save** để lưu lại thay đổi.