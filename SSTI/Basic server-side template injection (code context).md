<img width="1178" height="753" alt="Screenshot 2026-07-03 220319" src="https://github.com/user-attachments/assets/6cea866e-655f-44df-aa1e-481ff08c5492" />

Nhìn vào chức năng Preferred Name có vẻ nó không có cái gì đáng chú ý lắm và tôi cũng không có ý tưởng gì

<img width="1917" height="996" alt="Screenshot 2026-07-03 220625" src="https://github.com/user-attachments/assets/dcb48f05-0e21-4d18-877f-96c94327a247" />

Sau 1 lúc thì tôi xem thì thấy ở các phần comment khả năng có thể thay đổi tên của người comment và đúng là như vậy

<img width="1216" height="468" alt="Screenshot 2026-07-03 220822" src="https://github.com/user-attachments/assets/acb36f8b-5785-4c94-b445-1a60391d774a" />

<img width="1917" height="1006" alt="Screenshot 2026-07-03 220842" src="https://github.com/user-attachments/assets/b06e50ca-d43f-479c-acfa-7b4b875433c5" />

Từ đó tôi nghĩ có thể lợi dụng chức năng này để khai thác 

Kiểm tra thử 

<img width="1917" height="995" alt="Screenshot 2026-07-03 221102" src="https://github.com/user-attachments/assets/2fb96c89-ebc5-48c5-b0a5-0aa370953267" />

Có vẻ cần thoát ra khỏi dấu {{ trước khi khai thác 

<img width="1917" height="976" alt="Screenshot 2026-07-03 221220" src="https://github.com/user-attachments/assets/74915cff-cc90-4db1-b00a-a6de237e2f3a" />

<img width="1917" height="1020" alt="Screenshot 2026-07-03 221234" src="https://github.com/user-attachments/assets/8831ce2b-0c54-47cc-a1ff-b3d65dbb758e" />

Sau đó tôi cũng thử khai thác như trong thử thách đầu nhưng có vẻ không được mong muốn

<img width="1917" height="996" alt="Screenshot 2026-07-03 221414" src="https://github.com/user-attachments/assets/1e0b2e45-e060-401c-8b37-eca7e8746bf8" />

Đọc tài liệu 1 lúc thì có vẻ hàm trong Tornado template được viết như thế này

      {% apply *function* %}

Áp dụng vào bài ta có payload sau 

      {%import os%} {{os.system("ls -apls")}}

<img width="1917" height="843" alt="Screenshot 2026-07-03 222123" src="https://github.com/user-attachments/assets/a5d7530a-74af-47bb-aed0-c5262474a1a0" />

Thực hiện bước cuối để hoàn thành bài lab
