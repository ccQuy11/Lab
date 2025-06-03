![image](https://github.com/user-attachments/assets/aa3f10d8-41c4-4f82-a21c-4c1731f55dbe)
Mục tiêu: lấy file /etc/passwd

Bài này thì xác thực rằng đường dẫn được cung cấp bắt đầu bằng thư mục mong đợi. Hiểu đơn giản theo ý người viết là có thể file /etc/passwd đã nằm trong cái thư mục được cho

Nhớ đến phần pathtraversal của port swigger có vẻ đã đề cập nên quay về xem lại 
![image](https://github.com/user-attachments/assets/c06bfa6e-ed7e-403a-822f-a34e3e606f71)

Kế hoạch tấn công: thêm payload ../../../etc/passwd đằng sau /images/

Kết quả: ![image](https://github.com/user-attachments/assets/4c3356fe-7df6-41c1-95e2-7a1ad762c7c3)

01td
