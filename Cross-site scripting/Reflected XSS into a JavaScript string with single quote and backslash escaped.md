<img width="1328" height="707" alt="image" src="https://github.com/user-attachments/assets/fe3baf28-09f2-433e-b9b6-9ca7169ddf2a" />

Trong bài này tất cả dấu ' và dấu / đều đã bị mã hóa dẫn đến không thể kích hoạt hàm alert

<img width="1918" height="816" alt="image" src="https://github.com/user-attachments/assets/505c751d-5cab-4b09-baac-ad7b2c041e65" />

<img width="1277" height="168" alt="image" src="https://github.com/user-attachments/assets/5f50321f-a2e3-45f2-8b33-841d1ea61ffc" />

2 đoạn này là mã xử lí, trong đó nó kích hoạt chuỗi src với việc mã hóa các thành phần của URL tuy nhiên tôi tự hỏi liệu có thể thêm 1 đoạn mã nữa giấu bên trong đoạn mã kia không 

<img width="1465" height="458" alt="image" src="https://github.com/user-attachments/assets/5e1de2a6-8f1d-486d-a28d-88e9b7a72a70" />

Có vẻ không được nhưng nhìn xuống dưới thì có thể sau kí tự > thì nó không bị mã hóa nữa và được đưa vào document write, tôi tự hỏi xem nếu thêm 1 đoạn mã nữa ở đấy thì sẽ thế nào 

Mã khai thác

      <scr<script>ipt>alert(1)</scr</script><script>alert(1)</script>

<img width="1918" height="696" alt="image" src="https://github.com/user-attachments/assets/fd6c447c-8b12-4658-808e-d745fed50041" />

Ngồi 1 lúc check lại với đoạn mã <script>alert(1)</script><script>alert(1)</script> thì nhận ra có vẻ encodeURLcomponent chỉ mã hóa 1 lần còn lần sau thì kệ 
