![image](https://github.com/user-attachments/assets/62cc9b05-d5c3-41a4-9034-5d2e25479fef)
Mục tiêu: lấy file /etc/passwd

Bài này thì đề bài cho là ứng dụng xác thực tên tệp được cung cấp có phần mở rộng tệp mong muốn hay không. Hiểu đơn giản theo ý người viết thì là ở cuối mỗi file gì đó đều sẽ phải có 1 phàn đuôi mở rộng và nếu mất đi thì coi như không có file

Đọc đề bài thấy có chữ null byte nên đi search

Link bài

https://www.thehacker.recipes/web/inputs/null-byte-injection

https://owasp.org/www-community/attacks/Embedding_Null_Code

Sau khi đọc xong thì nhận ra có vẻ lab này đã có lỗ hổng bởi nếu cho thêm null byte kiểu %00 thì tự động cái đuôi mở rộng đấy sẽ bị xóa đi. Từ đó có thể thấy ứng dụng không xử lý đúng các ký tự kết thúc NULL hậu tố

Kịch bản tấn công: thêm đuôi %00.png vào sau /etc/passwd

Kết quả của payload: 

![image](https://github.com/user-attachments/assets/c45fbe46-37b0-4e96-8cbc-2bb0e95d3794)

![image](https://github.com/user-attachments/assets/ba5e693c-2489-450a-bcae-578b0fb8943f)
