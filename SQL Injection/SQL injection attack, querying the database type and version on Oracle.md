![image](https://github.com/user-attachments/assets/5689277f-2f51-4ab0-afbb-3326ed8a77cd)

Mục tiêu: hiển thị chuỗi database trong cơ sở dữ liệu 

Kịch bản tấn công: Sử dụng payload liên quan đến version của ORACLE

Như đề bài cho thì bài này nó sẽ liên quan đến ORACLE nên vào cheat code xem có kiếm được gì không

Check vào phần database 

![image](https://github.com/user-attachments/assets/374b9fb0-54b0-4135-ba86-f468026f4911)

Mở lab lên:

![Screenshot 2025-06-05 231005](https://github.com/user-attachments/assets/8d2b957e-1455-4c49-82da-b3a9d5feaa59)

Trong lab này thì chỉ có 2 cột nạp dữ liệu 

![image](https://github.com/user-attachments/assets/8859620d-5585-426c-959b-4d519cd501e2)

Nên có thể sử dụng payload 'UNION SELECT 'abc','def' FROM dual-- - tức là in cái abc,def từ bảng giả dual có sẵn trong ORACLE để check

Kết quả in ra:

![image](https://github.com/user-attachments/assets/42dac5a1-0a78-4745-a450-78bf9240c8d6)

Nó có vẻ đã in ra nên sử dụng lệnh từ cheat code để in ra version 

![image](https://github.com/user-attachments/assets/44e12821-04d6-4d5a-8355-897fc9a7c4d7)

Sử dụng payload 'UNION SELECT banner, NULL FROM v$version-- - để xem có ra không 

![image](https://github.com/user-attachments/assets/4d6d2619-cc19-4e5d-a097-b64106bd201f)

 
