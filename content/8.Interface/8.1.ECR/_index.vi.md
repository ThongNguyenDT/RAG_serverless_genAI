---
title: "Làm việc với ECR"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 8.1. </b> "
---

### Docker setup

Tải Docker nếu chưa có theo link bên dưới:

[Docker Download](https://www.docker.com/)

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image.png)

Tải xuống phiên bản phù hợp với thiết bị của bạn.

Sau khi cài đặt hoàn tất, bạn cần đăng nhập vào Docker Hub của mình.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%201.png)

Bạn có thể đăng nhập bằng Google, Github, hoặc tài khoản cá nhân của bạn.

Bạn có thể bỏ qua bước này.

Sau đó, truy cập vào mục **Images → Local**.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%202.png)

Hiện tại, bạn chưa có image nào và cần đẩy image của **interface lambda** lên **ECR**.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%203.png)

### Docker CLI test

Mở terminal và chạy lệnh sau:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%204.png)

Vậy là bạn đã hoàn tất setup Docker.

### Tạo ECR private **repository**

Truy cập **ECR** qua console:

[Elastic Container Registry - Home (amazon.com)](https://us-east-1.console.aws.amazon.com/ecr/home?region=us-east-1)

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%205.png)

Tiến hành tạo repo mới.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%206.png)

Ở mục **Visibility settings**, bạn có thể chọn *Private* hoặc *Public*.

{{% notice tip %}}
❗ Theo mình test thử thì **Lambda** không cho phép dùng public image.
{{% /notice %}}

Đặt tên tùy ý cho repo của mình. Lưu ý phải tuân theo các điều kiện của AWS.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%207.png)

Cuối cùng nhấn nút **Create**.

### Docker image build

Truy cập vào nơi chứa code **Lambda**.

Source code này bạn có thể lấy tại link Github dự án ở đầu bài.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%208.png)

Tại repo ECR bạn vừa tạo, sẽ có hướng dẫn đầy đủ để bạn build và đẩy code lên, việc của bạn là copy và dán vào terminal trong thư mục chứa code.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%209.png)

ECR hỗ trợ rất nhiều hệ điều hành cho bạn lựa chọn. Như mình đang dùng **Windows**, mình sẽ tiến hành chạy các lệnh sau.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2010.png)

Nếu gặp lỗi giống mình, có thể tham khảo thêm tại [StackOverflow](https://stackoverflow.com/questions/70393195/get-ecrlogincommand-is-not-recognized-as-the-name-of-a-cmdlet-function-scrip). Bạn phải cài các gói tool của AWS trước khi dùng lệnh.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2011.png)

Nếu gặp lỗi đăng nhập, có thể tham khảo thêm tại [AWS Forum](https://repost.aws/questions/QUKqrdl3lfR9ON8KnSP6FbzQ/getting-error-while-pushing-images-to-public-ecr) hoặc [StackOverflow](https://stackoverflow.com/questions/60807697/docker-login-error-storing-credentials-the-stub-received-bad-data).

{{% notice tip %}}
Cá nhân mình khi thực hiện các lệnh trên **Windows** cần cài thêm các gói phụ và gặp lỗi. \
Bạn có thể thử chạy các lệnh trên hướng dẫn **Linux** bằng **Powershell** giống mình.
{{% /notice %}}

Sau khi đăng nhập thành công:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2012.png)

Sau khi đăng nhập thành công, tiến hành build image:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2013.png)

Kết quả sau khi build:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2014.png)

### Docker push to ECR

Đặt tag phù hợp với repo của mình trước khi đẩy lên **ECR**:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2015.png)

Cuối cùng, đẩy image lên **ECR**:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2016.png)

Tá đa!

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2017.png)

### ECR with interface lambda

Thực hiện lại các bước:

- Tạo repo
- Build image
- Push image

Tương tự cho **Interface Lambda**.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%203.png)



