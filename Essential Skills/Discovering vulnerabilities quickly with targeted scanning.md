<img width="1135" height="629" alt="Screenshot 2026-05-25 084957" src="https://github.com/user-attachments/assets/1dd52adc-7dc0-42ed-885b-3439afcda019" />

Mục tiêu: xuất nội dung /etc/passwd trong 10 phút

<img width="1919" height="1018" alt="image" src="https://github.com/user-attachments/assets/0c2c4a45-2423-4afe-afe5-fccb9ccba220" />

Sử dụng active scanner vào 2 url là /product/stock với /product?productId=1

<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/c4ff09de-9bed-4686-ac47-51f344715f55" />

Trong /post/product phát hiện ra Out-of-band resource load vấn đề này cho phép attacker được dùng 1 url bên ngoài để gán vào payload, khi kích hoạt server sẽ phản hồi với hệ thống bên ngoài của attacker

Đưa url này vào repeater thay payload với link là link của Burp Collab

<img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/18b26ff4-0ee1-4e69-a780-cadd23a463f2" />

<img width="1919" height="1007" alt="image" src="https://github.com/user-attachments/assets/bc438de5-0b0c-4d3a-ab48-fba98a1f87ae" />

Có thể thấy Burp Collab đã nhận được phản hồi dù máy chủ không gây ra lỗi, có thể thử khai thác bằng cách thay url của nó thành file:///etc/passwd với việc parse='text'

Payload cuối:

    <nwp xmlns:xi="http://www.w3.org/2001/XInclude"><xi:include parse="text" href="file:///etc/passwd"/></nwp>

<img width="1919" height="1025" alt="image" src="https://github.com/user-attachments/assets/6d47a165-01d1-49f2-b80e-ad53934cf511" />

<img width="1919" height="1019" alt="image" src="https://github.com/user-attachments/assets/62c8fdf0-63cd-454a-9463-01a0186ffdcb" />
