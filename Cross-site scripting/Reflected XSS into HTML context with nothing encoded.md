![image](https://github.com/user-attachments/assets/750f5dec-5ce0-439a-842c-ad08b635c878)

Mục tiêu: gọi hàm alert

Lỗ hổng:  Reflected XSS

Reflected XSS xảy ra khi một ứng dụng nhận dữ liệu trong yêu cầu HTTP và đưa dữ liệu đó vào phản hồi ngay lập tức theo cách không an toàn

Mở lab ra vào thử search 1 cái gì đó 

![image](https://github.com/user-attachments/assets/9525dabe-fa5a-41b3-b75e-31aa387f0d2d)

Theo như lí thuyết thì có thể viết payload của reflected xss như sau 

      ?search=<script>....</script>

Mà như đề bài cũng bảo là sử dụng hàm alert nên payload cuối cùng sẽ như này 
           
           <script>alert(1)</script>

Kết quả 

![image](https://github.com/user-attachments/assets/7f8d3706-583d-4a08-bde7-41698e2cad8c)
