![image](https://github.com/user-attachments/assets/240c286a-d002-465d-8726-af0ae895e518)
Mục tiêu: truy xuất nội dung file để đọc được file /etc/passwd 
Bài này yêu cầu ta sử dụng lổ hổng  path traversal để có thể vượt qua và vào file /etc/passwd lấy thông tin 
Làm theo như solution thì sẽ vào burpsuite để chặn các tín hiệu tuy nhiên các dữ liệu trả về đều là productId và nó không thể trả về file /etc/passwd
![image](https://github.com/user-attachments/assets/4588d9ed-ffd4-4f56-aa06-c5d40403febc)

Ảnh khi sử dụng repeater để xem có thể lấy được file /etc/passwd không nhưng tất cả là không

Theo solution thì ta cần lấy đổi tên tham số tệp là file nhưng khi đổi từ productId thì nó cũng trả về kết quả là 0 solve

![image](https://github.com/user-attachments/assets/e5dc0a7b-b303-41ab-b278-98ae63a8e124)

Thử tham khảo video chữa nhưng có vẻ bài lab đã có sự thay đổi (maybe) nên lúc này có 1 kịch bản khác được lên là sẽ mở ảnh đấy trong 1 file khác cụ thể là chuột phải bấm open image in a new tab và thật bất ngờ khi nó đã xuất hiện tham số tệp filename
![image](https://github.com/user-attachments/assets/ea2ecdb1-7279-4dd8-af67-6eabb3a42d91)


Từ đây có thể sử dụng ../../../../etc/passwd để lấy được nội dung trong nó và solve bài lab này 
![image](https://github.com/user-attachments/assets/a1f1bee3-3a11-4701-bbb4-1244360c7474)
Ảnh của ../../../etc/passwd

![image](https://github.com/user-attachments/assets/9f8de66c-cc82-4bdf-883e-267fbf3cff9f)
Kết quả trả về sau khi solve ra 

![image](https://github.com/user-attachments/assets/9d212dbe-3352-4134-867b-951ca58a65e3)
Solve
