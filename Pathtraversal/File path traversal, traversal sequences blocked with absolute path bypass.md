![image](https://github.com/user-attachments/assets/8031cbcc-2b6c-4d51-8de4-e1705974c742)
Mục tiêu: lấy được file /etc/passwd

Bài này vẫn cho các file ảnh như bài trước nhưng tuy nhiên trang web đã chặn các kí tự ../../ nên không thể dùng cho bài này được

Kịch bản tấn công: dùng đường dẫn tuyệt đối 

Khái quát: đường dẫn tuyệt đối có format <protocol>://<domain>/<path> dùng xác định vị tri chính xác vị trí của một file hoặc một thư mục trong hệ thống tệp bắt đầu từ thư mục gốc
Ví dụ: filename=///etc/passwd
Vẫn như lần trước ta thử với ../../../../../etc/passwd tuy nhiên có vẻ như trang web đã chặn nên không thể thu được gì từ đây 
![image](https://github.com/user-attachments/assets/a18a9c1d-c453-4160-9d40-e8c44f6f1b1c)

Sau đó theo như đề bài gợi ý là đường dẫn tuyệt đối ta xóa phần 12.jpg đi và thay bằng ///etc/passwd để ra kết quả
![image](https://github.com/user-attachments/assets/a683e92b-4f50-40e6-94d1-6f48a2cedf0e)

GG
