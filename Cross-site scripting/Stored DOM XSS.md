<img width="1918" height="898" alt="image" src="https://github.com/user-attachments/assets/28a1673e-e61d-407e-b19b-c2d738d6dd4f" />

Nhập thông tin ở comment, sau khi nó nhận bật ctrl + U để xem web thay đổi như thế nào  

<img width="1917" height="827" alt="image" src="https://github.com/user-attachments/assets/7aa0a5b1-95ee-41f1-bc25-f01e7f1b2705" />

Nhìn trong đây có 2 đoạn script dùng để xử lí, nhấn vào loadCommentsWithVulnerableEscapeHtml.js

<img width="1918" height="852" alt="image" src="https://github.com/user-attachments/assets/0f58b7de-db17-4eb9-8bc6-bda90b82a707" />

Nhìn vào đây có 1 hàm tên là loadComments dùng để xử lí các comment mà người dùng đăng

    var xhr dùng để khai báo hàm XMLHttpRequest, hàm này dùng để thực hiện yêu cầu path đến 1 đường dẫn được chỉ định cùng với các tham số tìm kiếm của URL hiện tại

    xhr.onreadystatechange dùng để xử lí việc gọi thuộc tính thay đổi "readyState" của XMLHttpRequest, nó kiểm tra tình trang ready là 4 và status là 200

    xhr.open dùng để gọi để method Get nhằm nhận dữ liệu từ path chỉ định đén địa chỉ với các tham số tìm kiếm của URL  hiện tại 

    xhr.send thực hiện việc gửi yêu cầu HTTP

Tuy nhiên nhìn ở dưới có 1 hàm là escapeHTML dùng để encode các kí tự <> thành các kí tự của HTML. Tuy nhiên, replace() lại thường chỉ thay thế 1 lần cho nên ở những lần sau khi nhập <> sẽ không bị thay thế nữa

Kiểm chứng

<img width="1918" height="1068" alt="image" src="https://github.com/user-attachments/assets/da07ae92-d127-40b5-b8e7-9a349a14770b" />

Nhìn vào thẻ p có thể thấy đoạn <script>alert(1)<script> đã thoát ra khỏi dấu ngoặc kép từ đó chứng minh được suy luận là đúng, khai thác tiếp để lấy kết quả

    <><img src=1 onerror="alert(1)">

  <img width="1918" height="1058" alt="image" src="https://github.com/user-attachments/assets/190b0498-d8c6-4a45-97ac-0772d00180b1" />

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/4c8cfa81-d43b-46e7-95c6-86e64f1e3800" />
