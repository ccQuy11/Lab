![image](https://github.com/user-attachments/assets/b4663e6f-c379-4cac-bbc1-581aac40046a)

Mục tiêu: nâng cấp user thành quản trị viên 

Lỗ hổng: Kiểm soát truy cập bị hỏng do cấu hình nền tảng không đúng

Ở đây nó cho user và mật khẩu của admin nên vào bằng tk admin xem

![image](https://github.com/user-attachments/assets/285f6c85-cd46-4a29-95e5-3962da3ec682)

Ở đây nó có 3 user là admin carlos và wiener, trong khi carlos có thể lên admin thì wiener thì không nên có thể vứt vào trong burpsuite, cho carlos lên admin trước và dựa vào cái upgrade của carlos mà đổi cho wiener

![image](https://github.com/user-attachments/assets/382dd292-1ce5-4758-a84c-e88aa9088abc)

Thì ở đây là cái admin-role của carlos, thì sau đó đăng nhập lại user wiener và dán lại cookie của user đó vào trong cái của carlos cùng với đó là thay đổi cả method từ POST sang GET

![image](https://github.com/user-attachments/assets/40faec16-495f-44f1-b277-5a01567c2e65)

Kết quả

![image](https://github.com/user-attachments/assets/0a2187ed-35f5-457d-921a-c13bac9d89f4)
