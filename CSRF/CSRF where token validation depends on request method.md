![image](https://github.com/user-attachments/assets/6aa9359b-8129-4b5f-aa3a-639873bee382)

Mục tiêu:  khai thác để lưu trữ trang HTML sử dụng tấn công CSRF để thay đổi địa chỉ email của người xem.

Lỗ hổng : Xác thực mã thông báo CSRF phụ thuộc vào phương thức yêu cầu

Như tiêu đề thì ở đây sẽ thay đổi Request method của HTTP, cụ thể là từ POST sang GET

Vào trong trang Lab, đăng nhập user và thay đổi email

![image](https://github.com/user-attachments/assets/d6e286b5-ce93-4c2f-9f6c-9dd082608aba)

![image](https://github.com/user-attachments/assets/3e45d0a5-6fdd-4328-b6c5-f2d56dcde0b3)

Như ở ảnh đầu thì khi mà nhập đúng token csrf thì hệ thống xác thực đúng sẽ trả về kết quả còn nếu thay đổi thử 1 chữ trong đấy, hệ thống nhận ra sai sót thì sẽ không đồng ý

Ở đây thay đổi request method và xóa thử CSRF xem như nào 

![image](https://github.com/user-attachments/assets/1f2c1cb0-0b16-46cd-8245-de38f4b94982)

Ở đây có thể thấy là kể cả xóa csrf đi thì nó cũng không thể biết do đã bỏ qua, mở PoC tạo mã html và dán vào exploit server

![image](https://github.com/user-attachments/assets/59b24e49-9a0b-40ab-b6c3-9819ba74e86b)

Dán vào trong body và thay đổi email xem có nhận không

![image](https://github.com/user-attachments/assets/0aa9b45a-1889-40c1-80be-d380f416f216)

Có vẻ như nó đã nhận nên thay đổi thử 1 từ trong email và đưa vào victim 

![image](https://github.com/user-attachments/assets/585344f2-dafb-4739-a2cd-07180fc8e10e)

