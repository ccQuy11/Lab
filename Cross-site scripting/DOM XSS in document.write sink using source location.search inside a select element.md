<img width="1100" height="617" alt="image" src="https://github.com/user-attachments/assets/8dd6fa0f-29fa-46bb-921c-434a05ceba34" />

Thử nhấn vào 1 stock và vào src code xem thử

<img width="948" height="375" alt="image" src="https://github.com/user-attachments/assets/0707e764-c963-4018-ad95-7ea62bb9756a" />

Trong src code, đoạn mã đang được filter bởi thẻ <select>, khi attacker nhập payload thì đoạn mã logic vẫn sẽ chỉ nhận được mỗi cái Id của store và tên store được lưu trong Array

Ví dụ như khi user nhập payload bình thường 

    <script>alert(1)</script>

Lúc này đoạn payload sẽ được lưu trong biến store cùng với biến stores nhưng lúc này nó chưa thoát được cái tag <select> nên là kết quả vẫn sẽ ra là số lượng có sẵn ở mỗi chi nhánh. Cho nên, ta cần đóng lại thẻ tag này để có thể thêm payload vào

Payload cuối cùng

               storeId="></select><img%20src=1%2onerror=alert(1)>

<img width="1754" height="840" alt="image" src="https://github.com/user-attachments/assets/7ea5b1bf-90df-4752-920f-c45b4faafdc1" />
