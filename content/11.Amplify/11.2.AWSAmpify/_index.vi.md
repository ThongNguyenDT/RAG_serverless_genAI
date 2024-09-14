---
title: "Triển khai ứng dụng trên AWS Amplify"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 11.2. </b> "
---


## Đẩy mã nguồn UI lên Github

Bước đầu tiên, bạn cần sao chép thư mục UI ra khỏi dự án của bạn để tách biệt với git của dự án chính.

Vị trí của thư mục UI:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%204.png)

Sau khi sao chép đến vị trí mới, mở dự án của bạn trong terminal:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%205.png)

Và chạy các lệnh sau để đẩy mã nguồn lên Github:

```bash
git init
```

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%206.png)

Tiếp theo, commit mã nguồn với thông điệp:

```bash
git commit -m "first commit"
```

Nếu gặp thông báo về những thay đổi chưa được thêm vào git:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%207.png)

Thêm tất cả các tệp tin vào git:

```bash
git add .
```

Commit lại mã nguồn:

```bash
git commit -m "UI upload"
```

Sau khi thực thi lệnh này, bạn sẽ thấy các tệp tin đã được thêm vào git hiển thị trên terminal.

Thêm đường dẫn đến repo để đẩy mã nguồn:

```bash
git remote add origin <đường dẫn trong ảnh>
```

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%203.png)

Đẩy mã nguồn lên Github bằng lệnh:

```bash
git push -u origin main
```
Sau khi hoàn tất, truy cập vào repo của bạn để kiểm tra xem mã nguồn đã được đẩy lên hay chưa.

## Kết nối AWS Amplify với Github

Truy cập trang chủ của AWS Amplify:

[Amplify Console](https://us-west-2.console.aws.amazon.com/amplify/apps)

Chọn nút **Create new App**:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%208.png)

Tại giao diện tạo ứng dụng mới, chọn:

Ở đây, AWS Amplify hỗ trợ nhiều loại ứng dụng khác nhau, và trong dự án này, chúng ta sẽ sử dụng **Vite**.

Chọn vị trí mã nguồn của bạn:

- **Github**
- Nhấn nút **Next** để kết nối với Github của bạn.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%209.png)

Một cửa sổ hiện ra yêu cầu bạn cấp quyền truy cập cho tài khoản Github của mình:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2010.png)

Nhấn nút màu xanh để cấp quyền truy cập.

Nếu tài khoản của bạn thuộc về một tổ chức, hãy chọn chủ sở hữu của repo. Bạn có thể bỏ qua bước này nếu không liên quan đến tổ chức hoặc nếu tài khoản của bạn là tài khoản cá nhân.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2011.png)

Nhấn **Install**.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2012.png)

Xác thực MFA nếu cần.

Sau khi hoàn tất xác thực, cửa sổ sẽ đóng lại và kết nối giữa Github và AWS Amplify của bạn đã thành công.

## Triển khai ứng dụng

Bây giờ, chúng ta sẽ tiến hành triển khai ứng dụng.

Sau khi xác thực, bạn sẽ thấy danh sách các repo của mình:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2013.png)

Chọn repo của bạn và nhấn **Next**.

{{% notice tip %}}
Bạn cần chọn đúng nhánh chứa mã nguồn cần triển khai. Sau mỗi lần thay đổi mã nguồn trong nhánh đó, AWS Amplify sẽ tự động chạy lại quá trình triển khai.
{{% /notice %}}

Tiếp theo, đặt tên cho ứng dụng và nhấn **Next**:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2014.png)

Kiểm tra lại các bước và lưu:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2015.png)

Giao diện triển khai:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2016.png)

Sau khi quá trình triển khai hoàn tất:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2017.png)

Truy cập URL đã được tạo và đăng nhập bằng tài khoản của bạn để kiểm tra.

Nếu bạn gặp lỗi kết nối đến backend:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2018.png)

Chúng ta sẽ xử lý lỗi này trong bước tiếp theo.