---
title: "Kiểm tra tải tài liệu"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 10.2. </b> "
---

Khi cửa sổ tải tài liệu hiển thị như sau, điều đó có nghĩa là quy trình tải tài liệu của bạn đang hoạt động.

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2010.png)

Nếu gặp lỗi kết nối, hãy kiểm tra lại console của trình duyệt. Nếu thấy thông báo kết nối timeout, có thể do kết nối lần đầu, bạn có thể bỏ qua vì các lần sau sẽ hoạt động bình thường. 

Nếu gặp lỗi CORS, kiểm tra lại file **appconfig.json** xem tên bucket đã chính xác chưa, hoặc nếu bạn vừa bật CORS thì hãy đợi một lúc để các thay đổi có hiệu lực.

Nếu mọi thứ đã được thiết lập chính xác, giao diện sẽ hiển thị như sau:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2011.png)

## Thử nghiệm tải file

Bây giờ, thử tải một file lên. Trong quá trình tải, bạn sẽ thấy hai thông báo sau:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2012.png)

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2013.png)

Sau đó, bạn sẽ nhận được kết quả hiển thị trên giao diện như sau:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2014.png)

Hãy làm mới (refresh) lại trang để kiểm tra xem server đã cập nhật chưa. Nếu mọi thứ chạy ổn, kết quả sẽ như sau:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2015.png)

---

## Kiểm tra SQS

Kiểm tra xem SQS đã được kích hoạt chưa. Nếu SQS đã nhận được thông báo từ S3 và gửi sang cho Lambda, bạn sẽ thấy thông báo trong mục **Messages available** nếu hàm Lambda đang khởi động (cold start).

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2016.png)

Điều này chứng minh rằng hàm Lambda đã được kích hoạt thành công:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2017.png)
