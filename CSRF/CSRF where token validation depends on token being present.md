![image](https://github.com/user-attachments/assets/73f95f81-b429-452d-8b15-ac6000af0ca2)

Mục tiêu: Khai thác mã html, thay đổi email người dùng

Lỗ hổng: Xác thực token: là kiểu nếu như có token thì sẽ được xác thực tuy nhiên nếu không có thì server sẽ không xác thực được từ đó bỏ qua

Mở burpsuite đăng nhập user và password đồng thời thay đổi email

![image](https://github.com/user-attachments/assets/c5e99cf6-77e9-4d7f-9501-e19cb736d5ce)

Sau khi đưa phần /change-email vào repeater và xóa token đi thì có thể thấy máy chủ vẫn nhận nên có thể tạo PoC mà không cần đến token csrf

Tạo PoC csrf và tiêm vào body, view exploit xem

![image](https://github.com/user-attachments/assets/7f4cd896-c209-4ab3-9975-5219ba01f4bc)

Như vậy email vẫn được nhận bình thường nên về lại exploit server, thay đổi email và kết quả

![image](https://github.com/user-attachments/assets/92f5c5f2-66c4-4714-9b9b-827a9166e3d4)
