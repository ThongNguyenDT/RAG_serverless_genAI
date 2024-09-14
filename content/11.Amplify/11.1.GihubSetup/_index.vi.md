---
title: "Tạo Repository Trên Github"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 11.1. </b> "
---
## Bước đầu: Truy cập vào Github

Để bắt đầu, bạn cần truy cập vào trang chủ của Github qua đường dẫn sau:

[Github](https://github.com/)

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image.png)

## Tạo tài khoản Github

Nếu bạn chưa có tài khoản Github, bạn cần tạo một tài khoản mới. Quá trình tạo tài khoản gồm các bước sau:

1. Nhấn vào nút **Sign Up** trên giao diện chính.
2. Điền đầy đủ các thông tin cần thiết:
   - **Email** của bạn.
   - **Password** cho tài khoản.
   - **Username** duy nhất.
   - Giải quyết captcha để xác minh.
3. Mở **email** và tìm kiếm mail xác nhận từ Github. Nhấn vào liên kết trong email để hoàn thành xác nhận tài khoản.

Vậy là bạn đã hoàn tất việc tạo tài khoản Github thành công!

## Đăng nhập vào Github

### Đăng nhập trên trang web Github

Sau khi đã tạo tài khoản, bạn truy cập lại trang chủ của Github và thực hiện đăng nhập:

1. Nhấn vào nút **Sign In**.
2. Nhập thông tin đăng nhập của bạn:
   - **Email** hoặc **Username**.
   - **Password** của tài khoản.
3. Xác nhận captcha nếu được yêu cầu.

### Đăng nhập trên Git Local (Sử dụng terminal)

Khi bạn làm việc với git trên terminal, bạn cũng cần đăng nhập vào tài khoản Github. Để thực hiện việc này, chạy các lệnh sau:

```bash
 git config --global user.name "<Username>"
 git config --global user.email "<Email>"
```

## Tạo mới một Repository

Sau khi đăng nhập thành công, bạn sẽ thấy giao diện trang chủ của Github hiện ra. Để tạo một repository mới, làm theo các bước sau:

1. Nhấn vào nút **New** để bắt đầu tạo repo mới.

   ![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%201.png)

2. Trên giao diện tạo repo, bạn sẽ thấy các lựa chọn và cần điền thông tin như sau:

   ![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%202.png)

   - **Tên repository**: Đây là tên duy nhất cho repo của bạn. Bạn phải đặt tên sao cho không trùng lặp với các repo khác trong tài khoản của mình.
   - **Public** hoặc **Private**: Để việc triển khai dễ dàng, bạn nên để repo ở chế độ **Public**.
   - Các trường còn lại có thể để mặc định nếu bạn không có nhu cầu đặc biệt.

3. Sau khi hoàn thành, nhấn vào nút **Create** để tạo repository mới.

Khi repo được tạo thành công, bạn sẽ thấy giao diện như sau:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%203.png)