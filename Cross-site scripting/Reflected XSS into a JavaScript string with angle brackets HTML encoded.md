<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/25851459-907f-4790-84fe-e3a6e36f3941" />

Mô tả: This lab contains a reflected cross-site scripting vulnerability in the search query tracking functionality where angle brackets are encoded. The reflection occurs inside a JavaScript string. To solve this lab, perform a cross-site scripting attack that breaks out of the JavaScript string and calls the alert function.

Gõ thử <script>alert(1)<script> để xem kết quả

<img width="1897" height="924" alt="image" src="https://github.com/user-attachments/assets/484c8ed8-db9f-436a-8ff7-ccdf457a29e4" />

<img width="827" height="625" alt="image" src="https://github.com/user-attachments/assets/f5f3c8fc-93d3-4aaa-862e-fc5cc7ac0788" />

Trong phần source code thì giá trị tìm kiếm đã mã hóa dấu <. Theo 1 vài tìm hiểu thì khi mã hóa ví dụ như 

    '&lt;script&gt;alert(1)&lt;/script&gt

Lúc này ở phía máy khách nó sẽ hiển thị như một dạng chuỗi kí tự (như  '&lt;script&gt;alert(1)&lt;/script&gt) chứ không phải là HTML nghĩa là ta sẽ chỉ thấy mã code thay vì thấy link 

Vậy giờ ý tưởng ở đây là tìm cách cho đoạn mã khai thác thoát ra khỏi tag đầu và vô hiệu hóa các ký tự phía sau. Nhìn vào đoạn code có thể thoát ra bằng việc thêm 1 dấu ', ngoài ra để chú thích trong java có thể dùng dấu //, bên cạnh đó thì khi kết thúc 1 đoạn mã sẽ phần phải thêm cả ; để thông báo là câu lệnh này đã xong cho nên đoạn mã cuối cùng là 

    ';alert(1);//

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/b03f61cb-7fa1-4708-8286-9ef4972d009b" />
