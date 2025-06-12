![image](https://github.com/user-attachments/assets/dde375b6-2488-427e-a36b-380c545dbb00)

Mục tiêu: đăng nhập được vào carlos

Lỗ hổng: 2FA logic

Bài này liên quan đến logic xác thực 2FA, giúp người dùng có thể lợi dụng mã xác minh để đăng nhập vào sau khi thay đổi verify thành tên user khác trong burpsuite

Mở burpsuite và đăng nhập vào user wiener xem tình hình 

![image](https://github.com/user-attachments/assets/629e7a48-6a83-4750-8440-a0f106f2ca4c)

![image](https://github.com/user-attachments/assets/64b66386-03d3-4292-8a99-25ec2a93a8ec)

Nhìn qua thì có vẻ tất cả đều giống như bài 2FA trước nhưng ở đây carlos không có mật khẩu nên có thể hướng về việc brute force mfa của login2 như lí thuyết đã nói 

![image](https://github.com/user-attachments/assets/e24cbbf6-4887-4ecc-8418-7499d58238be)

Thử trong repeater thì có vẻ vẫn nhận nhưng đã sai mfa nên sẽ tiến hành bruteforce để tra ra mfa thật

![image](https://github.com/user-attachments/assets/28b37b54-953f-49bb-95b8-c2290e825b7e)

![image](https://github.com/user-attachments/assets/23991b41-3155-4469-92c3-53df395ee2f3)

Sau 1 lúc bruteforce thì ra mfa là 1235, check phần response lấy cookie và đường dẫn đưa vào

![image](https://github.com/user-attachments/assets/90bb1ceb-201f-44c5-93ab-2ca24eb08d8a)
