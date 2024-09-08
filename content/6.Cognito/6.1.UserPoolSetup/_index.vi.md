---
title: "Thiết lập UserPool"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 6.1. </b> "
---

### Truy Cập Dịch Vụ Cognito

Tại cửa sổ console, truy cập vào dịch vụ Cognito:

[Amazon Cognito > us-east-1 | Cognito | us-east-1](https://us-east-1.console.aws.amazon.com/cognito/v2/home?region=us-east-1)

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image.png)

### Cognito User Pool

Chúng ta chỉ login bằng email.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%201.png)

Chọn **Next**.

Ở bước chọn mật khẩu, bạn có thể chọn theo ý mình.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%202.png)

Ta không sử dụng MFA. Bạn có thể chọn các tùy chọn khác theo ý bạn.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%203.png)

Chọn **Next** và tiếp tục chọn **Next**.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%204.png)

Chọn như hình và **Next**.

Ở bước này, bên trái là dịch vụ gửi SNS cho doanh nghiệp. Trong bài lab này, bạn chỉ cần gửi thử nghiệm là được.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%205.png)

Bạn cần đặt tên cho user pool của bạn.

Để có thể truy xuất thông qua Amplify, bạn phải chọn checkbox như hình.

Nếu không cần domain, bạn có thể để mặc định.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%206.png)

Bạn phải cấu hình domain name phù hợp với quy định của Cognito.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%207.png)

Chọn **Public** để có thể đăng nhập từ Amplify. 

- App name có thể đặt tùy ý.
- URL callback là URL bạn muốn sau khi đăng nhập xong, có thể là URL của Amplify của bạn.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%208.png)

Tiếp tục và chọn **Create**.

Sau khi hoàn tất, bạn sẽ thấy giao diện như sau:

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%209.png)

Lưu ý hai mục sau:

- **User Pool ID**

Trong phần **App integration**, cuộn xuống dưới **App clients and analytics**.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%2010.png)

- **Client ID**

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%2011.png)

Hai mục này sẽ được sử dụng để cấu hình ở phần tiếp theo.
