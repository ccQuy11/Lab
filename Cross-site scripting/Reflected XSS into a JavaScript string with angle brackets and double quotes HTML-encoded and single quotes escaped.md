<img width="1182" height="592" alt="image" src="https://github.com/user-attachments/assets/3b938978-eece-44c4-b863-b32771e598c7" />

Trong bài này thì tất cả các dấu bị chặn trừ dấu ngoặc đơn

<img width="1471" height="486" alt="image" src="https://github.com/user-attachments/assets/bfb781c3-8172-4984-a19d-9d9db1b1ddb6" />

<img width="1228" height="113" alt="image" src="https://github.com/user-attachments/assets/a3d12772-0c7f-4d71-aae0-8f91516af252" />

Đọc script xử lí thì chỉ thấy nó mã hóa các phần của URL. Tuy nhiên nó chỉ nói dấu ngoặc nhọn hoặc ngoặc đơn chứ không nói gì về các dấu gạch chéo nên thử dấu gạch chéo để xem

<img width="1580" height="522" alt="image" src="https://github.com/user-attachments/assets/f3f6e561-f524-4f4d-ae9c-b9878eacd812" />

<img width="842" height="166" alt="image" src="https://github.com/user-attachments/assets/8ff8281d-0501-43fd-9f88-5ce42d0342d8" />

Có thể thấy dấu gạch chéo không bị mã hóa, kết hợp với dấu ngoặc đơn thì có thể có payload như sau  

    1/'-alert(1)// 

Nhưng payload này test lại thì không được nên thử thay đổi gạch chéo đầu xem thế nào 

<img width="1918" height="523" alt="image" src="https://github.com/user-attachments/assets/0be4c8a5-d1ae-494c-b2cd-45f26a62df9a" />
