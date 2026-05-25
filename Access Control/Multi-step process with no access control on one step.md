![image](https://github.com/user-attachments/assets/dca2cfa0-d7aa-4b9e-ae09-a6512ea79bf3)

Mục tiêu: đẩy user wiener lên làm admin

Lỗ hổng: Kiểm soát truy cập trong quá trình nhiều bước

Mở burpsuite lên và paste trang lab vào, đăng nhập vào admin và đẩy user carlos lên làm admin theo

![image](https://github.com/user-attachments/assets/8bf6b4ff-7a21-4c07-aa74-b3b766268765)

Nhìn qua thì có vẻ bài này sẽ na ná cách làm với bài của dạng Create Method-based access control can be circumvented tuy nhiên như đề thì nó sẽ cần nhiều bước chứ không chỉ một để nâng được wiener lên admin

Nhìn sơ qua ảnh thứ 2 thì http trả về 2 kết quả của việc nâng user carlos lên làm admin nên sẽ đưa cả 2 vào trong repeater, từ đó sao chép session của user wiener vào để hướng nó đến admin'

![image](https://github.com/user-attachments/assets/6e70c466-9e83-4596-877e-99c2b59ce433)

Nhìn qua thì có vẻ đã authorized nhưng mà vẫn còn 1 request nữa nên thử nốt

![image](https://github.com/user-attachments/assets/4adca4bc-f5ca-4739-941f-2f187a75416a)

Ổn rồi 

![image](https://github.com/user-attachments/assets/a371d55d-5910-4fd4-a64b-3e60ea93685f)
