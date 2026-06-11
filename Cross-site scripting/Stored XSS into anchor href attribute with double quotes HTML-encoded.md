<img width="1232" height="584" alt="image" src="https://github.com/user-attachments/assets/f2f4482d-7ac0-44a1-9917-dcdcfd2ed4bc" />

Mô tả: This lab contains a stored cross-site scripting vulnerability in the comment functionality. To solve this lab, submit a comment that calls the alert function when the comment author name is clicked.

Truy cập vào lab, thử thả 1 comment với website tự chọn của người dùng và nhấn submit

<img width="1919" height="807" alt="image" src="https://github.com/user-attachments/assets/ef6dbfb8-33ac-4982-8ec3-d11e9c11dd91" />

Khi quay lại blog và bấm vào tên người comment có thể dẫn đến trang web mà người comment đã dán vào 

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/8837c2cd-1699-495d-8446-753bcaf586eb" />

Trong phần HTTP history của Burp Suite, kiểm tra url post?postId có thể tìm thấy tất cả thông tin cùng với đó là đường link mà ta đã gắn vào

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/067fb083-8c11-45d5-adc6-57c68394d661" />

Phần href chính là phần mà user đã gắn đường link vào tuy nhiên, phần scheme không chỉ có mình https mà còn có cả ftp, http hay là javascript

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/0601fc15-fa08-4f83-9aab-1cb55fbcf0b8" />

Khi tra thử cách để gắn đường dẫn javascript thì có 1 ví dụ như thế này

<img width="1914" height="732" alt="image" src="https://github.com/user-attachments/assets/a7060211-e367-4cb9-ba90-c188c5180529" />

Trong đó javascript là scheme của url còn <script> là mã thực thi. Do đó có thể thử với url như sau: 

    javascript:alert(1)

<img width="1919" height="1054" alt="image" src="https://github.com/user-attachments/assets/f3c2408c-3989-4103-b06f-a855d8f3f2e1" />

<img width="1919" height="1057" alt="image" src="https://github.com/user-attachments/assets/dfd51e19-05c9-4ad9-942e-03dbab4e7177" />

