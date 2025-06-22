![image](https://github.com/user-attachments/assets/6a7eeece-6399-4020-814e-53c8566592a6)

Mục tiêu: sử dụng máy chủ khai thác để lưu trữ trang HTML sử dụng tấn công CSRF để thay đổi địa chỉ email của người xem.

Lỗ hổng: Mã CSRF không liên kết với người dùng.

Ở bài này một vài mã csrf được duy trì để trở thành mã toàn cầu nên chỉ cần lấy được mã này là có thể solve được bài

Vào thay đổi email của user wiener và đăng nhập vào email của user carlos

![image](https://github.com/user-attachments/assets/a9453cd7-c4ef-4f60-b07d-aa967c30ee9d)

Như ở trong đề bài dã nói là có thể lấy token csrf của user khác để thay đổi token cho csrf của user người dùng nên trong phần user của carlos có thể thấy 1 mã csrf mới, lấy thử mã này và thay vào token trong phần /change_email của user wiener

![image](https://github.com/user-attachments/assets/47c0d7fc-0567-4ac5-89a5-268e0009bf34)

Như ở đây thì có vẻ thay đổi token thì web vẫn nhận nên tạo 1 PoC csrf, đưa nó vào exploit server và send nó thử xem

![image](https://github.com/user-attachments/assets/64b5c140-221e-4e1f-b7d3-ebc05e031d57)

