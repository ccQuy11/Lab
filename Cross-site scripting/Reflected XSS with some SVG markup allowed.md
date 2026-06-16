<img width="1182" height="431" alt="image" src="https://github.com/user-attachments/assets/f0dccae4-6925-4062-8f6b-553313f4a0c4" />

Lab này đã chặn tất cả các tag ngoại trừ 1 vài tag SVG được chấp nhận

SVG(Scalable Vector Graphics) có thể được nhúng trực tiếp vào HTML, nó có thể điều chỉnh kích thước và không giảm chất lượng khi phóng to thu nhỏ

<img width="1918" height="402" alt="image" src="https://github.com/user-attachments/assets/4d1582b9-2db9-4279-854c-5238b718acc9" />

Có thể thấy khi nhập tag bình thường vào thì WAF sẽ chặn, thử đưa vào trong intruder để kiểm tra thử xem có tag nào có thể sử dụng không

<img width="1912" height="707" alt="image" src="https://github.com/user-attachments/assets/976099b2-efbc-47cd-8e70-b1f6efc0da52" />

Có thể thấy chỉ có 4 tag có thể sử dụng trong này, có cái animateTransform khá lạ, tìm kiếm ra thì nó phụ trách tạo hiệu ứng động cho phần tử mục tiêu

<img width="1847" height="736" alt="image" src="https://github.com/user-attachments/assets/a52e7537-164b-409c-8f07-289f59c4adc8" />

Sau khi đã tìm ra tag, tiếp tục tương tự để tìm ra event 

<img width="1386" height="533" alt="image" src="https://github.com/user-attachments/assets/272b5325-18c9-4ce0-81ed-eadcfe926b96" />

<img width="1756" height="743" alt="image" src="https://github.com/user-attachments/assets/5de8ffa9-2b65-41e7-8b25-bbb06b09eb12" />

Chỉ có 1 event duy nhất là onbegin, nó được kích hoạt ngay khi hoạt ảnh bắt đầu, tức là khi animateTransform được kích hoạt thì onbegin cũng sẽ được kích hoạt luôn 

Như vậy ý tưởng khai thác là viết 1 đoạn mã svg lồng vào đó là animateTransform, trong Transform sẽ được lồng vào onbegin để khi animateTransform được kích hoạt thì event sẽ được kích hoạt cùng luôn

<img width="1908" height="781" alt="image" src="https://github.com/user-attachments/assets/e1dd6987-95e9-4657-a61e-210213cdb591" />
