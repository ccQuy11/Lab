![image](https://github.com/user-attachments/assets/f589af0e-bfaa-47c6-b4b6-3c5fc8f22321)

Mục tiêu: lấy user và passwd 

Lỗ hổng trong passwd dựa trên mật khẩu

Ở bài này không khác gì bài trước nên làm theo các bước cũ

![image](https://github.com/user-attachments/assets/40825eb5-a295-4346-9331-3b66314aec71)

Sau khi bruteforce xong kiểm tra thì thấy tất cả đều dính 1 cái đó là invalid user and passwd cho nên ném vào filter, sử dụng negative search để tìm ra cái không bị negative search

Trong Burp Suite, Negative Search được sử dụng để lọc ra các kết quả không chứa một chuỗi hoặc mẫu (pattern) cụ thể trong phần Search của các tab như HTTP history, Proxy, Target, Repeater, v.v.

![image](https://github.com/user-attachments/assets/8e3d5deb-6ba3-4b20-bb1d-0117ac289fce)


Sau khi xác định được user thì thay đổi lại payload cho passwd và tìm ra pass đúng cho nó 

![image](https://github.com/user-attachments/assets/311498cd-e8f6-4ca3-85ab-9c260796f64e)

Nhập cả 2 vào 

![image](https://github.com/user-attachments/assets/d1eefde3-f4a6-41c3-aa77-b67388d0a8f3)
