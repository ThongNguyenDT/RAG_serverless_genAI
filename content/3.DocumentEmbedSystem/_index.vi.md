---
title: "Thiết Lập Hệ Thống Xử Lý Document Từ Người Dùng"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

Trong phần này, chúng ta sẽ cùng nhau thiết lập một hệ thống nhận tài liệu từ người dùng, lưu trữ lại và tự động gửi thông báo. Hệ thống này sử dụng hàng đợi để tối ưu hóa lưu lượng và cải thiện hiệu suất xử lý.

#### Cụ thể, các bước tiến hành bao gồm:

1. [Tạo Dead Letter Queue](3.1.deedletterqueue/)
2. [Tạo LanceDB Vector Bucket](3.2.lancedbvectorbucket/)
3. [Tạo Documents Bucket](3.3.documentsbucket/)
4. [Tạo Document Processing Queue](3.4.documentprocessingqueue/)
5. [Thiết lập Document bucket đẩy thông báo sang SQS](3.5.s3notificationtosqs/)
6. [Thiết lập CORS](3.6.addcors/)
