<img width="1281" height="742" alt="image" src="https://github.com/user-attachments/assets/6bcf692d-5b3c-4412-a5df-aa573869238e" />

Bài này yêu cầu người dùng lấy được key và submit

Test thử với payload đơn giản

<img width="1852" height="593" alt="image" src="https://github.com/user-attachments/assets/68012aef-aced-479b-98bb-e29f395f45f1" />

Có thể thấy trang web này được xây dựa vào Django template, đi tra thử các tài liệu về nó tôi thấy có cái này

<img width="1518" height="697" alt="image" src="https://github.com/user-attachments/assets/ba3589c6-15b8-498d-9ee6-d481e45921a4" />

    {% debug %}

Lệnh này sẽ show tất cả các module, thư viện được dùng để gỡ lỗi trong cái template này, dò từng cái tôi thấy có cái này 

<img width="470" height="157" alt="image" src="https://github.com/user-attachments/assets/be49161f-8296-45a0-9677-c61d6b97df46" />

Tra thử trong tài liệu thì thấy nó có chứa SECRET_KEY, gõ lệnh thì nó hiện key 

<img width="1895" height="817" alt="image" src="https://github.com/user-attachments/assets/10e9e0f7-38f2-4a08-8fcf-3def24b8dc60" />

<img width="1917" height="981" alt="image" src="https://github.com/user-attachments/assets/f71fa2ba-9a65-4df3-9ea5-d53d431b189c" />
