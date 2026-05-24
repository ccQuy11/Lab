<img width="1919" height="1015" alt="image" src="https://github.com/user-attachments/assets/b71a7b36-09c3-4742-aded-69f0884cbd4b" />

Mục tiêu: trích xuất nội dung trong /home/carlos/secret

<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/1dd3b37b-e377-4c83-bd5a-70cba2a8912d" />

Trong bài này, attacker chỉ có thể khai thác thông qua tải ảnh lên và không thể thay đổi nội dung trong Burp Repeater nên có thể dùng 1 công cụ tên là Exiftool để chèn thêm nội dung vào ảnh

Exiftool là 1 thư viện Perl độc lập nền tảng, đồng thời là một ứng dụng dòng lệnh dùng để đọc, ghi và chỉnh sửa thông tin meta trong nhiều loại tệp khác nhau. 

Ví dụ về 1 lệnh trong Exiftool 

<img width="1919" height="980" alt="image" src="https://github.com/user-attachments/assets/6f25aed6-1acd-4309-b46a-fc9f36e8bc4a" />

Chèn nội dung chứa mã độc hại vào trong 1.jpg 

<img width="1919" height="417" alt="image" src="https://github.com/user-attachments/assets/f5702fbe-604e-4975-97a8-ad520fa7a835" />

Việc thêm START END vào trong để người dùng có thể dễ dàng đọc nội dung trích xuất

Upload lại vào trong lab và lấy kết quả   

<img width="1919" height="807" alt="image" src="https://github.com/user-attachments/assets/c0ca2abf-85d4-471a-a2eb-67cf3fa84981" />

<img width="1917" height="977" alt="image" src="https://github.com/user-attachments/assets/6ecfe025-7258-4c3b-877e-11196919dca2" />
