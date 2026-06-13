<img width="1200" height="672" alt="Screenshot 2026-06-13 143731" src="https://github.com/user-attachments/assets/5bd7240b-7ce2-4e16-b2c7-e39157a1283a" />

Tất cả các thẻ đã bị chặn trừ thẻ tùy chỉnh.

<img width="1907" height="767" alt="image" src="https://github.com/user-attachments/assets/0c5db977-cb96-4478-ae3d-461925b2abee" />

Chạy thử thì chỉ có 4 payload này là trả về kết quả còn lại bị chặn hết 

Do không có ý tưởng nên tôi đi tìm sự giúp đỡ và có 1 payload như thế này

    <custom-tag onmouseover='alert("xss")'>

<img width="1918" height="941" alt="image" src="https://github.com/user-attachments/assets/f25bbda9-109a-4d88-a59b-8775ed28cc71" />

onmouseover xảy ra khi bấm chuột vào phần tử

Sau đó tôi tìm được 1 payload khác 

    <custom onfocus='alert(document.cookie)'  id = 'x' tabindex= '1' >

onfocus dùng để kích hoạt sự kiện khi một phần tử nhận tiêu điểm, biến nó thành phân tử đang hoạt động và sẵn sàng cho người dùng, nó thường xảy ra khi người dùng nhấp, di chuyển chuột đến hoặc chạm phần tử đó

id đóng vai trò là mã định danh duy nhất của phần tử trong tài liệu, giúp lựa chọn phần tử dễ dàng hơn thông qua CSS và JavaScript

tabindex='1' là quy trình ưu tiên cho tiêu điểm của onfocus khi di chuyển giữa các phần tử bằng phím tab

<img width="1918" height="1077" alt="image" src="https://github.com/user-attachments/assets/e395482e-5bf7-41fe-bed0-08b597a52a32" />

Tuy nhiên nhìn vào solution thì thấy phải thêm cả #x để nó tập trung vào id kia, nó sẽ chạy xss luôn, còn không phải làm thủ công

Payload solution

<img width="1872" height="897" alt="image" src="https://github.com/user-attachments/assets/6fd2ff1c-6d21-406b-b6cd-938b318bdc69" />

Ý tưởng ở đây là nạn nhân chuyển hướng đến đường dẫn của attacker  chạy mã độc trên trình duyệt nạn nhân và nó sẽ chuyển địa chỉ trình duyệt của nạn nhân đến trình duyệt của attacker

<img width="1918" height="887" alt="image" src="https://github.com/user-attachments/assets/ac6161f1-f9db-4c8a-897d-a7baf3f4f8c1" />
