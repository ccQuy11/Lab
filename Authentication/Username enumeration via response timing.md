![image](https://github.com/user-attachments/assets/d2a971dd-fa5a-4d98-8dca-0becccad1639)

Mục tiêu: lấy được user và passwd

Lỗ hổng: Xác thực thông qua thời gian phản hồi (maybe)

Trong bài này có 1 loại tiêu đề mới tên X-Forwarded-For dùng để ác định địa chỉ IP gốc của máy khách kết nối với máy chủ web thông qua máy chủ proxy .

Cú pháp:

X-Forwarded-For: <client>, <proxy>

X-Forwarded-For: <client>, <proxy>, …, <proxyN>

Mở burpsuite lên và nhập user lẫn passwd vào 

![image](https://github.com/user-attachments/assets/72a5c17e-23ac-4bc6-a448-18e2cb298dd4)

Đưa /login vào trong repeater để test trước, thêm X-Forwarded-For vào cùng với số ngẫu nhiễn xem nó phản hồi 

![image](https://github.com/user-attachments/assets/fccd6955-e92a-4715-9d72-9b6c1547f5fd)

Có vẻ vẫn ok nên đưa nó về intruder

Ở trong Intruder có 2 cái cần bruteforce, 1 là số của X-Forwarded-For ( trong khoảng 1 - 100 do chỉ có 100 pass) và 2 là username( cho trước), sử dụng PitchFork để tấn công do nó hữu ích trong yêu cầu đầu vào khác nhau nhưng có liên quan được chèn vào nhiều nơi trong yêu cầu.

Với phần passwd nên viết càng dài càng tốt để kéo dài thời gian phản hồi

![image](https://github.com/user-attachments/assets/552124a5-0216-4c93-bc83-705a6d91d3f2)

Nhìn qua đây có thể thể user accounts có thời gian response dài nhất nên mặc định nó là user của bài

Chuyển qua passwd với cách cũ

![image](https://github.com/user-attachments/assets/0072cc69-3cad-4519-a022-597f7125cf70)

Pass monitoring trả về 302 nghĩa là máy chủ đã nhận đúng user và passwd 

![image](https://github.com/user-attachments/assets/27d023f5-fe24-4ec6-91e3-5ad081041f0e)

