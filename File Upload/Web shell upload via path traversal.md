<img width="1180" height="364" alt="image" src="https://github.com/user-attachments/assets/7fe68307-b56c-4de4-9df1-74c710100a94" />

Mục tiêu: Trích xuất nội dung trong /home/carlos/secret

Trong bài này máy chủ đã cấu hình để ngăn chặn việc người dùng khai thác mã độc thông qua upload nội dung file ảnh tuy nhiên nó có thể bypass bằng việc kết hợp với cả Path Traversal

Path Traversal là phương thức cho phép attacker sử dụng các chuỗi kí tự như ../ để di chuyển lên một cấp trong chuỗi thư mục

<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/417c571e-8bf6-4495-8264-0ce6d8ee2631" />

<img width="1919" height="1014" alt="image" src="https://github.com/user-attachments/assets/6a97e2d9-5ff0-4790-ab04-fd72df6a9840" />

Việc khi thác mã độc hại trông qua path /file/avatars/1.php đã bị chặn và nếu mở nó sẽ chỉ mở dưới dạng văn bản thuần túy

<img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/e01514ff-fca8-4db7-b91e-6c978d543be7" />

Việc sử dụng chuỗi ../ được chấp nhận nhưng server cũng có cơ chế để phát hiện và ngăn chặn nên thử encode cái chuỗi kí tự này đi 

<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/3ff86b1d-a62f-4606-b43d-bf9dbe11937d" />

Bằng cách filter / với %2f thì server đã chấp nhận và từ đó có thể khai thác để lấy nội dung

<img width="1919" height="992" alt="image" src="https://github.com/user-attachments/assets/3054a66e-1eb2-49ca-b5c8-7ca53a54a19f" />

<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/eac7c9cd-438b-48fb-9584-2ab5a1cebde5" />
