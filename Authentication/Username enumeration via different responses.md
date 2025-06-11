![image](https://github.com/user-attachments/assets/a1eaf138-fd74-4564-8f48-1570696b63d1)

Mục tiêu: lấy được user và passwd từ danh sách

Lỗ hổng trong liệt kê người dùng

Trong bài này ngoài lab ra nó còn cho 2 file 1 là user và passwd rất dài nên nghĩ ra bruteforce;

Bruteforce là khi kẻ tấn công sử dụng hệ thống thử và sai để đoán thông tin đăng nhập hợp lệ của người dùng. Các cuộc tấn công này thường được tự động hóa bằng cách sử dụng danh sách từ của tên người dùng và mật khẩu

Vào burpsuite vứt đoạn http có đường dẫn /login vào intruder, đưa vào scope 2 phần user và passwd mình đã viết giả, sử dụng sniper và kéo danh sách đấy vào payload

![image](https://github.com/user-attachments/assets/d95cf306-8976-4aad-a32f-47f0cf3d774a)

Kia là payload của passwd

Bật start attack và quan sát độ dài của các payload thì thấy có 1 payload dài hơn các cái còn lại với username là  arcsight  nên có thể mặc định đây là username, viết lại cái username đấy vào còn lại giữ nguyên đối với payload passwd

Sau 1 thời gian chờ đợi là hành phúc thì có 2 cái length nó ngắn hơn cái còn lại tuy nhiên có 1 cái status code là 302 tức là server đã đồng ý nên passwd đấy chính xác là passwd của bài 

![image](https://github.com/user-attachments/assets/47ce34cb-7df3-48d5-a2db-af481e8159ae)

![image](https://github.com/user-attachments/assets/a4f3f015-ab7b-40e9-a20e-880928035f94)

