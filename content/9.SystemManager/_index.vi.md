---
title: "Cấu hình System Manager Parameter Store"
date :  "`r Sys.Date()`" 
weight : 9
chapter : false
pre : " <b> 9. </b> "
---

Trong phần này, chúng ta sẽ cùng nhau cấu hình **System Manager Parameter Store** để quản lý các tham số cần thiết cho hệ thống API. Việc sử dụng Parameter Store giúp bạn lưu trữ và quản lý dữ liệu một cách an toàn, dễ dàng truy cập trong các ứng dụng khác nhau.

## Truy cập vào System Manager

Tại cửa sổ **console** của AWS, tìm kiếm và truy cập vào dịch vụ **System Manager**.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image.png)

### Truy cập Parameter Store

Trong giao diện **System Manager**, tìm đến **Parameter Store** để bắt đầu quản lý các tham số.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%201.png)

## Tạo Parameter

Khi ở giao diện **Parameter Store**, bạn tiến hành tạo các tham số bằng cách nhấn vào **Create parameter**.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%202.png)

Tiếp theo, bạn cần tạo 3 tham số giống như hình mẫu.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%203.png)

- Đặt tên **<StackName>**, tham số này bạn có thể lấy từ **appconfig.json** trong hệ thống của mình.

```text
/<StackName>/default/contextFooter/

/<StackName>/default/noContextFooter/

/<StackName>/default/promptHeader/
```

- Đối với bài lab này, chỉ cần chọn **Standard** vì nó miễn phí và đủ dùng.
- Loại tham số sẽ là **String**, và **Data Type** sẽ là **Text**.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%204.png)

Ở phần **value**, bạn truy cập vào mã nguồn sau đó copy nội dung cần thiết vào tham số.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%205.png)

Cuối cùng, nhấn **Save** để hoàn tất việc tạo các tham số.