![image](https://github.com/user-attachments/assets/9b2c05c6-d4c8-4341-9393-299d252791e0)

Mục tiêu: xóa user carlos

Lỗ hổng: Có vẻ lỗi kiểm soát truy cập thông qua email

Ở bài này có vẻ như tất cả mọi cách đều không dùng được nhưng trong phần solution nó có gợi ý là trong phần update emaill có thể thêm roleid là 2 bởi nó sẽ dẫn đến admin

Mở burpsuite lên 

![image](https://github.com/user-attachments/assets/74ae5bb7-93c5-4db1-8ae7-27b4920a4df6)

Nhìn qua thì ở phần response thì roleid là 1 tức là chỉ ở user và bài bắt roleid là 2

Ném nó qua phần repeater:

![image](https://github.com/user-attachments/assets/ee126725-7234-4618-ba35-f64cda9e0008)

Ở đây có 1 file json là phần {"email":"mama1@test.ca"}

File json là   viết tắt của JavaScript Object Notation, là một kiểu định dạng dữ liệu tuân theo một quy luật nhất định mà hầu hết các ngôn ngữ lập trình hiện nay đều có thể đọc được. JSON là một tiêu chuẩn mở để trao đổi dữ liệu trên web.

![image](https://github.com/user-attachments/assets/b6a88f9d-7cd1-4eb7-88ae-866f5226b071)

Nghĩa là ở đây có thể thêm phần roleid vào và send để thay đổi vai trò của user

![image](https://github.com/user-attachments/assets/e6975cc6-4f48-4f08-8cc8-1b82d8657931)

Ở phần response thì roleid đã là 2 nên quay về web viết vào đường dẫn /admin sẽ dẫn đến  phần users và xóa user carlos

![image](https://github.com/user-attachments/assets/cae08629-856a-496d-a170-21efda48c8b3)
