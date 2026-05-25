![image](https://github.com/user-attachments/assets/d81a31ed-99ad-4764-8c83-29572568beae)

Mục tiêu: vào được tài khoản admin và xóa user carlos

Lỗ hổng: IDOR phân quyền theo chiều dọc

Đề bài bảo ta đăng nhập vào administrator sau đó lấy mật khẩu từ trong đó ra

Bật burpsuite và dán cái link lab vào, thay đổi id=administrator

![image](https://github.com/user-attachments/assets/3f0cc8ae-be62-4b1b-96cb-9c181e8a843f)

Sau khi đổi thành công sang admin vào phần response của id=administrator và tập trung vào phần passvwd, copy phần đấy và đăng nhập lại vào rồi xóa carlos đi

![image](https://github.com/user-attachments/assets/8248abfb-e21a-4ce3-8066-27a6607689b3)
